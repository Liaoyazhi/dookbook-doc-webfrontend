TOPICS: <dialog>

# `<dialog>`

**HTML`<dialog>`元素** 代表对话框或其他交互式组件，例如检查器或窗口。

|  |  |
| :-- | :-- |
| **内容分类** | 流内容，切片根 |
| **允许的内容** | 流量内容 |
| **标签遗漏** | 没有，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 任何接受流程内容的元素 |
| **允许的 ARIA 角色** | `alertdialog` |
| **DOM 接口** | `HTMLDialogElement` |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。 tabindex属性不能在`<dialog>`元素上使用。

| 属性 | 描述 |
| :-- | :-- |
| `open` | 指示对话框是活动的并且可以交互。 如果未设置open属性，则不应向用户显示该对话框。

## 使用说明

- 通过使用属性method="dialog"指定元素，可以将[`<form>`](/zh-hans/webfrontend/<form>)元素集成到对话框中。 提交此类表单后，对话框将关闭，其`returnValue`属性设置为所使用的表单的“提交”按钮的值。
- 他的`::backdrop` CSS伪元素可用于在`<dialog>`元素后面设置样式，例如在模式对话框处于活动状态时使无法访问的内容变暗。 仅当对话框元素通过`HTMLDialogElement.showModal()`显示时才绘制背景。

## 示例

### 简单的例子

```html
<dialog open>
  <p>Greetings, one and all!</p>
</dialog>
```

### 进阶范例

当单击“更新详细信息”按钮时，此示例将打开一个包含表单的弹出对话框。

```html
<!-- Simple pop-up dialog box containing a form -->
<dialog id="favDialog">
  <form method="dialog">
    <p><label>Favorite animal:
      <select>
        <option></option>
        <option>Brine shrimp</option>
        <option>Red panda</option>
        <option>Spider monkey</option>
      </select>
    </label></p>
    <menu>
      <button value="cancel">Cancel</button>
      <button id="confirmBtn" value="default">Confirm</button>
    </menu>
  </form>
</dialog>

<menu>
  <button id="updateDetails">Update details</button>
</menu>

<output aria-live="polite"></output>
```

```javascript
(function() {
  var updateButton = document.getElementById('updateDetails');
  var favDialog = document.getElementById('favDialog');
  var outputBox = document.getElementsByTagName('output')0];
  var selectEl = document.getElementsByTagName('select')0];
  var confirmBtn = document.getElementById('confirmBtn');

  // “Update details” button opens the <dialog> modally
  updateButton.addEventListener('click', function onOpen() {
    if (typeof favDialog.showModal === "function") {
      favDialog.showModal();
    } else {
      alert("The dialog API is not supported by this browser");
    }
  });
  // "Favorite animal" input sets the value of the submit button
  selectEl.addEventListener('change', function onSelect(e) {
    confirmBtn.value = selectEl.value;
  });
  // "Confirm" button of form triggers "close" on dialog because of method="dialog"]
  favDialog.addEventListener('close', function onClose() {
    outputBox.value = favDialog.returnValue + " button clicked - " + (new Date()).toString();
  });
})();
```
