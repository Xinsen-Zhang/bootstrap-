# input group 的学习

## 使用 input-group 来表示一组 input
* 可以在输入框的前端(后端)加入修饰内容
    * `.input-group-prepend` 或者 `input-group-append`
        * 用`span`包裹`.input-group-text`
## wrapping
* 为了在 input-group 之内成功的容纳自定义的表格,默认的是.flex-wrap
* 可以手动设置.flex-nowrap

```html
<div class="input-group flex-nowrap">
  <div class="input-group-prepend">
    <span class="input-group-text" id="addon-wrapping">@</span>
  </div>
  <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="addon-wrapping">
</div>
```

## sizing
* 通过`.input-groput-*`控制输入框的大小,内容的大小也会跟着一起进行修改
    * `.input-group-sm`
    ```html
    <div class="input-group input-group-sm align-items-center">
        <div class="input-group-prepend">
            <span class="input-group-text">@</span>
        </div>
        <input type="text" class="form-control">
    </div>
    ```
    * `.input-group` 默认大小
    ```html
    <div class="input-group align-items-center">
        <div class="input-group-prepend">
            <span class="input-group-text">@</span>
        </div>
        <input type="text" class="form-control">
    </div>
    ```
    * `.input-group-large` 大
    ```html
    <div class="input-group input-group-lg align-items-center">
        <div class="input-group-prepend">
            <span class="input-group-text">@</span>
        </div>
        <input type="text" class="form-control">
    </div>
    ```
    
## checkbox 和 radio
* 可以使用 checkbox 或者 radio 来代替 span 包裹的 text
    * checkbox 多选
    ```html
    <!--checkbox-->
    <div class="container py-2 border">
        <div class="row justify-content-center">
            <div class="text-info font-weight-bolder">Checkbox</div>
            <div class="w-100"></div>
            <div class="input-group">
                <div class="input-group-prepend">
                    <div class="input-group-text">
                        <input type="checkbox" name="checkbox" id="checkbox" aria-label="Checkbox for the following input text">
                    </div>
                </div>
                <input type="text" name="text" class="form-control" id="checkbox-text" placeholder="Please input" aria-label="Text input with checkbox">
            </div>
        </div>
    </div>
    ```
    * radio 单选
    ```html
    <div class="container py-2 border">
        <div class="row justify-content-center">
            <div class="text-info font-weight-bolder">Radio</div>
            <div class="w-100"></div>
            <div class="input-group">
                <div class="input-group-prepend">
                    <div class="input-group-text">
                        <input type="radio" name="radio" id="radio" aria-label="Radio for the following input text">
                    </div>
                </div>
                <input type="text" name="text" class="form-control" id="radio-text" placeholder="Please input" aria-label="Text input with radio">
            </div>
        </div>
    </div>
    ```
## Multiple input
* 在且仅在`.input-group`中支持多个`input`标签分割样式
```html
<div class="input-group">
    <div class="input-group-prepend">
        <span class="input-group-text">FirstName and LastName</span>
    </div>
    <input type="text" name="firstname" id="firstname" placeholder="firstname" class="form-control">
    <input type="text" name="lastname" id="lastname" placeholder="lastname" class="form-control">
</div>
```
## Multiple addons
* 不仅支持多个 input, 也支持多个 add-ons, 而且也能 text, checkbox 和radio 进行混合
```html
<div class="container py-2 border">
    <div class="row">
        <div class="input-group">
            <div class="input-group-prepend">
                <span class="input-group-text">$</span>
                <span class="input-group-text">0.00</span>
            </div>
            <input type="text" class="form-control">
        </div>
        <div class="w-100"></div>
        <div class="input-group">
            <input type="text" class="form-control">
            <div class="input-group-append">
                <div class="input-group-text">
                    <input type="checkbox">
                </div>
                <div class="input-group-text">
                    <input type="radio">
                </div>
            </div>
        </div>
    </div>
</div>
```

## Button adons
```html
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <button class="btn btn-outline-secondary" type="button" id="button-addon1">Button</button>
  </div>
  <input type="text" class="form-control" placeholder="" aria-label="Example text with button addon" aria-describedby="button-addon1">
</div>

<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Recipient's username" aria-label="Recipient's username" aria-describedby="button-addon2">
  <div class="input-group-append">
    <button class="btn btn-outline-secondary" type="button" id="button-addon2">Button</button>
  </div>
</div>

<div class="input-group mb-3">
  <div class="input-group-prepend" id="button-addon3">
    <button class="btn btn-outline-secondary" type="button">Button</button>
    <button class="btn btn-outline-secondary" type="button">Button</button>
  </div>
  <input type="text" class="form-control" placeholder="" aria-label="Example text with two button addons" aria-describedby="button-addon3">
</div>

<div class="input-group">
  <input type="text" class="form-control" placeholder="Recipient's username" aria-label="Recipient's username with two button addons" aria-describedby="button-addon4">
  <div class="input-group-append" id="button-addon4">
    <button class="btn btn-outline-secondary" type="button">Button</button>
    <button class="btn btn-outline-secondary" type="button">Button</button>
  </div>
</div>
```

## dropdown button segment
* 利用 multiple button 可以做到 segment 的效果
```html
<div class="input-group">
    <input type="text" class="form-control" placeholder="Please Input Here">
    <div class="input-group-append">
        <button class="btn btn-outline-secondary" type="button">Action</button>
        <button class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-expanded="false" aria-haspopup="true" type="button"></button>
        <span class="sr-only">Toggle dropdown</span>
        <div class="dropdown-menu">
            <a href="#" class="dropdown-item">Action 1</a>
            <a href="#" class="dropdown-item">Action 2</a>
            <a href="#" class="dropdown-item">Action 3</a>
            <div class="dropdown-divider" role="separator"></div>
            <a href="#" class="dropdown-item">Seperator Link</a>
        </div>
    </div>
</div>
```

## Custom forms
### custom select
* `select`标签上使用`.custom-select`
```html
<div class="input-group">
    <div class="input-group-prepend">
        <span class="input-group-text">Options</span>
    </div>
    <select class="custom-select">
        <option value="" selected>Choose...</option>
        <option value="1">Option 1</option>
        <option value="2">Option 2</option>
        <option value="3">Option 3</option>
        <option value="4">Option 4</option>

    </select>
</div>
```

### custom upload
* 把`.custom-file`放在包裹代码块上
    * 把`.custom-file-input`放在`input:file`上
    ```html
    <div class="input-group">
        <div class="custom-file">
            <input type="file" class="custom-file-input" id="file" multiple>
            <label for="file" class="custom-file-label">Choose files</label>
        </div>
        <div class="input-group-append">
          <button class="btn btn-outline-secondary bg-light" type="submit">Submit</button>
      </div>
    </div>
    ```

