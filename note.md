[Resource](https://youtu.be/j97QtHf0CHY)

Điểm tương đồng giữa vuejs và reactjs
---

| vuejs | reactjs |
|---|---|
| Data | State |
| VueX | Redux |
| Vue router | router |
| component | component|
| props | props|


Cài đặt
---

```
npm install -g @vue/cli
OR
yarn global add @vue/cli
```

Tạo project:
```
vue create my-project
# OR
vue ui
```

Cách chạy web
---
`npm run serve`


Cấu trúc thư mục
---
**public**: chứa file index.html hiển thị trên browser

**src**: sourcode
 - main.js: file gốc
 - App.vue: component gốc. 
   - có 3 thành phần:
     - template: html -> phần hiển thị. Bắt buộc phải có 1 element (vd thẻ <div>), và element này sẽ là parent của tất cả các element khác thì mới run dc
     - script: js -> phần xử lý
     - style: css -> làm đẹp. Hỗ trợ scss. Chỉnh được scoped.
        ```
            <style>
                // dùng chung cho tất cả các component 
            <style>


            <style scoped>
                // chỉ dùng cho component đó thôi
            <style>
        ```

    1 file component bất kỳ đều chứa code html, js và cả css. Khi build thì vue sẽ nhặt từng phần ra và build. Cách viết này có ưu điểm là khi viết component nào thì chúng ta chỉ tập trung vào file của component đó thôi, ko cần phải nhảy qua nhảy lại giữa các file (tính đóng gói)

 - components: chứa các component con. Mỗi 1 component đều bắt buộc phải có 1 root element (vd thẻ <div>)
 - assets: chứa các file hình ảnh, âm thanh, font
  
**dist**: folder release lên môi trường product.  
    Folder này dc tạo ra khi ta run lệnh `npm run build`


Cách tạo component
---
1. tạo file xxx.vue
    1 file component cơ bản
    ```html
    <template>
        <div> <!-- cái này là root element -->
        </div>
    </template>

    <script>
    export default {
    props: {

    }
    </script>

    <!-- Add "scoped" attribute to limit CSS to this component only -->
    <style scoped>

    </style>

    ```

2. import component trên tại `App.vue`

    `import xxxyyy from './components/xxx.vue'`

Cơ chế 2 ways binding
---
[video giải thích cụ thể](https://youtu.be/j97QtHf0CHY?t=2458)


bind dữ liệu 2 chiều là khi ta khai báo trong luồng xử lý và dùng nó trong phần hiển thị. Trong phần hiển thị ta cũng có thể thay đổi value xong phần xử lý nên nó có tính 2 chiều

```html
<template>
    <div>
        <input type="text" v-model="name" /> <!-- 3. sử dụng ở đây. Và thẻ input nên nó có thể thay đổi giá trị của biến dc dùng trong v-model. v-model sẽ làm nhiệm vụ liên kết biến này vs biến mà chúng ta khai báo trong phần xử lý -->

        {{name}} <!-- 2. sử dụng ở đây -->
    </div>
</template>

<script>
export default {
    data() { // 4. data này phải là hàm thì trên phần hiển thị có thay đổi gì thì nó mới gọi hàm và cập nhật giá trị mới nhất dc. Hàm này luôn luôn trả về 1 object chứa các dữ liệu mà chúng ta cần
        return {
            name: "this is a name binding" // 1. khai báo ở đây
        }
    },
}
</script>
```

Lifecycle
---
Vòng đời của component trong vue

![image](https://dltqhkoxgn1gx.cloudfront.net/img/posts/how-to-use-lifecycle-hooks-in-vue3-1.png)

những khung có chữ màu đỏ dc gọi là các hook (là những hàm mà chúng ta móc vào)

[video giải thích](https://youtu.be/j97QtHf0CHY?t=3287)

Binding
---
 - value binding: {{ xxx }}
 - property binding: bind thuộc tính của 1 element theo một property đã khai báo
    ```
    <h1 v-bind:id="id">

    data() {
        return {
            id: "abc"
        }
    },
    ```

 - cách viết `v-bind:property="variable"` hoặc cách viết tắt `:property="variable"`
    - style and class binding thì dùng `:class`
    ```
    <span :class="{done: task.status}">{{ task.title }} </span> 
    ```
    thẻ span sẽ dc asign class `done` khi variable `task.status = true`

Model
---
Liên kết element với property

Event handling
---
 - bắt sự kiện từ các element
 - cách dùng: `v-on:eventName="something"`
    - ví dụ: `v-on:click="doSomething()"`
    - viết tắt `@` -> `@click`
 - prevent default event : huỷ bỏ event mặc định của element
 - debounce: hoãn event lại một khoảng thời gian rồi mới thực thi
 - ref: ánh xạ đến chính element

 Conditional rendering
 ---
 - v-show: ẩn hiện 1 element theo điều kiện
    - cách dùng `v-show="isShow"`
 - v-hide: ngược lại với `v-show`
 - v-if: giống ở `v-show` ở chỗ điều khiển element ẩn hiện. Nhưng khác ở chỗ dùng `v-show` thì element vẫn còn trên DOM và chỉ thay đổi ờ style, còn `v-if` thì element bị xoá trên DOM luôn
  - v-el

List rendering
---
 - v-for

Methods
---
hàm của vue object

watch
---
theo dõi sự thay đổi của 1 biến realime. 
vd: khi nhập liệu mà có 1 character nào đó mà hệ thống ko cho phép dùng thì cảnh báo lên cho người dùng liền


hooks
---
***mounted***

hàm giống như contructor. Khi object được gắn lên trên trang html thì nó sẽ chạy hàm này đầu tiên.
Trong này chúng ta có thể gọi những hàm init


props
---
 - dữ liệu lấy từ component cha sang component con
 - cách dùng: ở nơi gọi thì `:propsName="variable"`
 - có 2 cách lấy
    - cách 1 : dùng mảng tên các props. `props : ['taskProp1', 'taskProp2']`
    - cách 2: định nghĩa đối tượng
    ```
    props: {
        taskProp1 : { // cách 2: define object
            type: Object,
            default: function() {
                return { title: 'My journey with Vue', status: false }
            }
        }
    },
    ```

filters
---
tính năng này chỉ có trên vue2 và sang vue 3 thì ko thể sử dụng dc nữa


