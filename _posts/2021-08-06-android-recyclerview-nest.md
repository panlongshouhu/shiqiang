---
layout: post
title: NestedScrollView(RecyclerView)嵌套RecyclerView(同方向)从入门到放弃
categories: android
description: NestedScrollView(RecyclerView)嵌套RecyclerView(同方向)从入门到放弃
keywords: android, NestedScrollView
---

## &nbsp;&nbsp;&nbsp;&nbsp;由于业务发展的需要或者版本的快速迭代，导致页面会遇到NestedScrollView(RecyclerView)嵌套RecyclerView的这种需求实现方式，在此记录一下具体的几种可行方式和踏坑问题，以供参考。

### 1. NestedScrollView用于页面布局的滑动:  

一、android:descendantFocusability=""属性(焦点夺取问题)  
属性的值有三种：  
beforeDescendants：viewgroup会优先其子类控件而获取到焦点  
afterDescendants：viewgroup只有当其子类控件不需要获取焦点时才获取焦点  
blocksDescendants：viewgroup会覆盖子类控件而直接获得焦点  
通常我们用到的是第三种，即在Item布局的根布局加上android:descendantFocusability=”blocksDescendants”的属性  

二、android:fillViewport="true"属性(填充满滑动布局)  
属性fillViewport解决android布局不能撑满全屏的问题  

### 2. 嵌套的业务更新的场景为前期使用NestedScrollView增加View的滑动功能，后期业务需要添加RecyclerView列表的底部追加功能:  

一、当嵌套发生，并且RecyclerView的数据量不大并且一次性加载完成，可使用NestedScrollView嵌套RecyclerViewVIew，并且需要把RecyclerViewVIew设置属性RecyclerView.setNestedScrollingEnabled(false)使RecyclerViewVIew的无法滑动，全部交给NestedScrollView滑动进行页面的控制。  

二、当RecyclerView数据量大的情况或者需要分页加载的情况分几种踏坑方式：  

2.1.NestedScrollView嵌套RecyclerView什么常规设置，滑动错乱，无法灵敏滑动  

2.2.NestedScrollView嵌套RecyclerView，并且设置RecyclerView.setNestedScrollingEnabled(false)，内存增大，RecyclerView的复用机制失效，有多少item创建多少ViewHolder  

2.3.NestedScrollView嵌套RecyclerView设置RecyclerView的高度，进行动态控制，虽然NestedScrollView实现父类嵌套滑动类，但是滑动依然无法灵敏滑动，滑动跳跃问题  

2.4.NestedScrollView设置setNestedScrollingEnabled(false)，只能局部滑动，无法全部VIew进行整屏滑动 

**总结：**  
因为业务的变更，如果RecyclerView数据量不大，可以使用2.2的方式。  
如果数据量大或者有分页加载，必须使用RecyclerView一个，进行分type布局或者通过addHeaderView进行实现，禁止NestedScrollView嵌套RecyclerView实现。
