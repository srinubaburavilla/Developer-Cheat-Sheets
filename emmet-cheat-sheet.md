
# Emmet Cheat Sheet | Emmet Tutorial | Emmet Pocket Reference | How to use Emmet 
## div+p+strong  
```html
<div></div>
<p></p>
<strong></strong>
```        
## div>p>strong
```html
<div>
    <p>
        <strong></strong>
    </p>
</div>
```                   
## div.container
```html
<div class="container"></div>
```  
## button.btn.btn-enabled.btn-white
```html
<button class="btn btn-enabled btn-white"></button>
```  
## div#container
```html
<div id="container"></div>
```  
## input:password
```html
<input type="password" name="" id="">
```  
## div[name=divLogin]
```html
<div name="divLogin"></div>
``` 
## div[title="Welcome Page"]
```html
<div title="Welcome Page"></div>
``` 
## a{Click me}
```html
<a href="">Click me</a>
``` 
## ul>li*5
```html
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```  
## Label{$}*3
```html
<Label>1</Label>
<Label>2</Label>
<Label>3</Label>
``` 
## Label{Lable $}*3
```html
<Label>Lable 1</Label>
<Label>Lable 2</Label>
<Label>Lable 3</Label>
``` 
## ul>li{Item_$}*5
```html
<ul>
    <li>Item_1</li>
    <li>Item_2</li>
    <li>Item_3</li>
    <li>Item_4</li>
    <li>Item_5</li>
</ul>
``` 
## div>p>ul>li*2>a+div>p.success
```html
<div>
    <p>
        <ul>
            <li>
                <a href=""></a>
                <div>
                    <p class="success"></p>
                </div>
            </li>
            <li>
                <a href=""></a>
                <div>
                    <p class="success"></p>
                </div>
            </li>
        </ul>
    </p>
</div>
```
## div>(p>ul>li*2>a)+div>p.success
```html
<div>
    <p>
        <ul>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </p>
    <div>
        <p class="success"></p>
    </div>
</div>
``` 
## table>thead>th+tr>td
```html
<table>
    <thead>
        <th></th>
        <tr>
            <td></td>
        </tr>
    </thead>
</table>
```
## td[rowspan=2 colspan=3 title]
```html
<td rowspan="2" colspan="3" title=""></td>
``` 
## table>(thead>th{Header $}*5)+(tr>td{Cell_$}*3)*3
```html
<table>
    <thead>
        <th>Header 1</th>
        <th>Header 2</th>
        <th>Header 3</th>
        <th>Header 4</th>
        <th>Header 5</th>
    </thead>
    <tr>
        <td>Cell_1</td>
        <td>Cell_2</td>
        <td>Cell_3</td>
    </tr>
    <tr>
        <td>Cell_1</td>
        <td>Cell_2</td>
        <td>Cell_3</td>
    </tr>
    <tr>
        <td>Cell_1</td>
        <td>Cell_2</td>
        <td>Cell_3</td>
    </tr>
</table>
``` 

