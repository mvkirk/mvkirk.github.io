---
layout: post
title:  "Angular 2 ViewChild ElementRef"
date:   2016-11-23
categories: [angular2]
---
You need to manipulate a DOM Element inside your Angular 2 component. You could use `document.getElementBy..` but it's not the Angular way.

With Angular 2 you can bind your html elements directly on a attribute of your component as a `ViewChild`

`my-component.component.html`
{% highlight html linenos %}
<div>
  <h1>Example</h1>
  <div #myDivElement class="center">
    ...
  </div>
</div>
{% endhighlight %}

`my-component.component.ts`
{% highlight javascript linenos %}
import {Component, OnInit, ElementRef, ViewChild} from '@angular/core';

@Component({
  selector: 'yourselector',
  templateUrl: 'my-component.component.html'
})
export class MyComponent implements OnInit {
  @ViewChild('myDivElement') myElement: ElementRef;

  constructor() {}

  ngOnInit(): void {
    // You can manipulate your element with this.myElement.nativeElement
    console.log(this.myElement.nativeElement.innerHTML);
  }
}
{% endhighlight %}

[https://angular.io/docs/ts/latest/api/core/index/ElementRef-class.html](https://angular.io/docs/ts/latest/api/core/index/ElementRef-class.html)
