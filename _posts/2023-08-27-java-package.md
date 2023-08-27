---
layout: post
title: "java 패키지, 생성자"
description: "Java 패키지, 생성자"
categories: [java 패키지, 생성자]
tags: [java]
redirect_from:
  - /2023/08/19/
---
# java package, method 기초

```java
public class Main{
  public static void main(String[] args){

     // Car 클래스의 객체 생성
        Car car1 = new Car();
        car1.brand = "bmw";
        car1.model = "x5";
        car1.year = 2023;
        car1.setPrice(100000);
        System.out.println("car1의 브랜드는"+car1.brand);

        Car car2 = new Car("benz");
        car2.model = "E-class";
        car2.year = 2022;
        car2.setPrice(200000000);
        System.out.println("car2의 브랜드는 "+car2.brand+" "+"가격은 " + car2.gerPrice());

        Car car3 = new Car("audi", "Sclass", 2023, 10000000);
        int salePrice = car3.calculateSalePrice(10);
        System.out.println(("car3의 브랜드, 모델, 연식, 가격은")+ salePrice);
  }
}
```
위의 코드를 복사해 실행시켜보면, 에러가 뜨는 것을 볼 수 있다. brand, model, year, 등 Car class의 method가 정의되지 않은 채로 실행했기 때문이다.

이를 해결하려면 Car class를 정의해야 한다.
***

Car class의 정의는 다음과 같이 이루어진다.
```java
public class Car {

    //맴버변수, 필드, 변수
    public String brand;
    public String model;
    public int year;


    //메서드 만드는 법
    //접근제어자 리턴타입 메서드명 (파라미터1, 파라미터2...){ 로직 }
    private int price;

    //기본 생성자
    Car(){}
    //생성자 오버로딩


    //brand만 받는 생성자
    Car(String brand){
        this.brand=brand;
    }
    //brand, price, model, year
    Car(String brand, String model, int year, int price){
        this.brand = brand;
        this.model = model;
        this.price = price;
        this.year = year;
    }
    //getter
    public int gerPrice(){
        return this.price;
    }

    //setter
    public void setPrice(int price) {
        this.price = price;
    }

    public int calculateSalePrice(int discount) {
        return this.price -discount;
    }
}
  ```
위의 코드에서는 Car class의 다양한 method가 형성되었음을 볼 수 있다. 
