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