---
title: Angular.js
category: JavaScript libraries
---

    <html ng-app="nameApp">

### 列表 (ng-repeat)

    <ul ng-controller="MyListCtrl">
      <li ng-repeat="phone in phones">
        {{phone.name}}
      </li>
    </ul>

### 模型 (ng-model)

    <select ng-model="orderProp">
      <option value="name">Alphabetical</option>
      <option value="age">Newest</option>
    </select>

### 定义一个模块

    App = angular.module('myApp', []);

    App.controller('MyListCtrl', function ($scope) {
      $scope.phones = [ ... ];
    });

### 防止控制器被压缩

    App.controller('Name', [
      '$scope',
      '$http',
      function ($scope, $http) {
      }
    ]);

    a.c 'name', [
      '$scope'
      '$http'
      ($scope, $http) ->
    ]

### 服务

    App.service('NameService', function($http){
      return {
        get: function(){
          return $http.get(url);
        }
      }
    });

在控制器中携带参数进行调用，将利用promise来从服务器返回数据。

    App.controller('controllerName',
    function(NameService){
      NameService.get()
      .then(function(){})
    })

### 指令

    App.directive('name', function(){
      return {
        template: '<h1>Hello</h1>'
      }
    });

在HTML中将使用 `<name></name>` 来渲染你的模板 `<h1>Hello</h1>`

### HTTP

  App.controller('PhoneListCtrl', function ($scope, $http) {
    $http.get('/data.json').success(function (data) {
      $scope.phones = data;
    })
  });

参考:

 * https://github.com/angular/angular-seed
 * https://angularjs.org/
