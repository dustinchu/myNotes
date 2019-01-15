# CSS


vaadin  CSSlayout RWD CSS

第一種   直接使用  ValoTheme 

DOC
https://vaadin.com/api/com/vaadin/ui/themes/ValoTheme.html




LAYOUT_HORIZONTAL_WRAPPING
公共靜態最終  字符串 LAYOUT_HORIZONTAL_WRAPPING
當沒有足夠的空間時，使Horizo??ntalLayout將包含的組件換成新行。


參考   第一種方法 感覺比較簡單!
```

HorizontalLayout row = new HorizontalLayout();
        row.addStyleName(ValoTheme.LAYOUT_HORIZONTAL_WRAPPING);
        row.setSpacing(true);
        addComponent(row);

        Panel panel = new Panel("Normal");
        panel.setContent(panelContent());
        row.addComponent(panel);
```


第一種方法不行的話 參考

https://vaadin.com/docs/v8/framework/themes/themes-responsive.html


第二種方法  
```
CssLayout status = new  CssLayout();
        status.setStyleName("responsive");
        status.setSizeFull();
```
        //響應式需要添加 才會讀取目前寬度高度 但感覺不太正常!待確認
        Responsive.makeResponsive(status);

這樣 會依照寬度換行   



寬度不可設定 不然不會換行
```
  Panel p_status = new Panel();
        p_status.setStyleName("panel");
        status.addComponent(p_status);
```
可在panel下的 水平佈局中 設定 SizeFull  
讓他撲滿容器

例如!!↓
```
  HorizontalLayout layout2 = new HorizontalLayout();
        layout2.setStyleName("horizontalContainer");
        layout2.setSizeFull();
        layout2.setMargin(true);
        layout2.setSpacing(true);
```



* 需加在csslayout下 然後判斷寬度 在用CSS去修改panel的CSS 寬度 這樣就不會有錯誤

* CSS可用這種 有&的
```
.responsive {
    &[width-range~="0-300px"] {
      .panel{
        width: 100%!important;
        height: 100%
      }
    }
    &[width-range~="301-500px"] {
      .panel{
        width: 100%!important;
        height: 100%
      }
    }
    &[width-range~="501px-"] {
      .panel{
        width: 50%!important;
        height: 100%
      }
    }
```

 
* 也可用這種

```
   .myresponsive {

      overflow: scroll;
    }
  /* Small size */
  .myresponsive[width-range~="0-801px" ] {
    .panel{
      width: 100%!important;
      height: 100%
    }
  }
  
  ```
  
  