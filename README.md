# Standard PHP Library 문서 번역 및 샘플 코드

모든 문서의 내용은 [PHP 공식 사이트](https://php.net)에서 가져 왔습니다.

## 소개

표준 PHP 라이브러리 (SPL)는 일반적인 문제를 해결하기위한 인터페이스 및 클래스 모음입니다.

이 확장을 빌드하는 데 외부 라이브러리가 필요하지 않으며 기본적으로 PHP 5.0.0에서 사용 가능하고 컴파일됩니다.

SPL은 일련의 표준 데이터 구조, 객체를 순회하는 반복기 집합, 인터페이스 집합, 표준 예외 집합, 파일 작업을위한 여러 클래스를
제공하며 [spl_autoload_register()](https://www.php.net/manual/en/function.spl-autoload-register.php) 와 같은 함수 집합을 제공합니다.

## 데이터구조

SPL은 일련의 표준 데이터 구조를 제공합니다.

### Double Linked List

---
Double Liked List(DLL)은 양방향으로 서로 연결된 노드 목록입니다. 반복자의 작업, 양쪽 끝에 대한 액세스, 노드 추가 또는 제거는 기본 구조가 DLL 인 경우 O(1)의 비용이 듭니다. 따라서 스택
및 큐에 대한 적절한 구현을 제공합니다.

* SplDoubleLinkedList
  * SplStack
  * SplQueue

### Heap

---
힙은 힙 속성을 따르는 트리와 같은 구조입니다. 힙에 전역인 구현 된 비교 메서드를 사용하여 비교할 때 각 노드는 자식보다 크거나 같습니다.

* SplHeap
  * SplMaxHeap
  * SplMinHeap
* SplPriorityQueue

### Array

---
배열은 인덱스를 통해 액세스 할 수있는 연속적인 방식으로 데이터를 저장하는 구조입니다. PHP 배열과 혼동하지 마십시오. PHP 배열은 실제로 정렬 된 해시 테이블로 구현됩니다.

* SplFixedArray

### Map

---
맵은 키-값 쌍을 보유하는 데이터 구조입니다. PHP 배열은 정수/문자열에서 값으로의 맵으로 볼 수 있습니다. SPL은 객체에서 데이터로의 맵을 제공합니다. 이 맵은 객체 세트로도 사용할 수 있습니다.

* SplObjectStorage


## 반복자

SPL은 객체를 순회하는 Iterator 세트를 제공합니다.

### SPL Iterators Class Tree

---
* ArrayIterator
  * RecursiveArrayIterator
  

* EmptyIterator
* IteratorIterator
  * AppendIterator
  * CachingIterator
    * RecursiveCachingIterator
  * FilterIterator
    * CallbackFilterIterator
      * RecursiveCallbackFilterIterator
    * RecursiveFilterIterator
      * ParentIterator
    * RegxIterator
      * RecursiveRegxIterator
    * InfiniteIterator
    * LimitIterator
    * NoRewindIterator
  
  
* MultipleIterator
* RecursiveIterator
  * RecursiveTreeIterator
  

* DirectoryIterator(SplFileInfo의 확장)
  * FilesystemIterator
    * GlobIterator
    * RecursiveDirectoryIterator


## 인터페이스

SPL은 인터페이스 세트를 제공합니다. 

[미리 정의된 인터페이스와 클래스](https://www.php.net/manual/en/reserved.interfaces.php)참조

### Interface List

---
* Countable
* OuterIterator
* RecursiveIterator
* SeekableIterator
* SplObserver
* SplSubject


## 예외

SPL은 일련의 표준 예외를 제공합니다.

[미리 정의된 예외](https://www.php.net/manual/en/reserved.exceptions.php)참조

### SPL Exceptions Class Tree

---
* LogicException(Exception의 확장)
  * BadFunctionCallException
    * BadMethodCallException
  * DomainException
  * InvalidArgumentException
  * LengthException
  * OutOfRangeException


* RuntimeException(Exception의 확장)
  * OutOfBoundsException
  * OverflowException
  * RangeException
  * UnderflowException
  * UnexpectValueException


## SPL 함수

