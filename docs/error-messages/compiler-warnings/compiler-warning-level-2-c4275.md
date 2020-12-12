---
description: '詳細情報: コンパイラの警告 (レベル 2) C4275'
title: コンパイラの警告 (レベル 2) C4275
ms.date: 02/08/2019
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 0dd212d7439b73c28a5426574b72ff8150abe93c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173650"
---
# <a name="compiler-warning-level-2-c4275"></a>コンパイラの警告 (レベル 2) C4275

> dll インターフェイスではないクラス '*class_1*' が dll インターフェイスクラス '*class_2*' のベースとして使用されています

エクスポートされたクラスは、エクスポートされていないクラスから派生しました。

[__Declspec (dllexport)](../../cpp/dllexport-dllimport.md)を使用してクラスをエクスポートする際にデータが破損する可能性を最小限に抑えるには、次の点を確認してください。

- すべての静的データには、DLL からエクスポートされた関数を介してアクセスします。

- クラスのインラインメソッドで静的データを変更することはできません。

- 静的データを使用する CRT 関数やその他のライブラリ関数は、クラスのインラインメソッドでは使用されません。

- 静的データにアクセスする CRT 関数やその他のライブラリ関数は、インラインクラス関数では使用できません。

- (インライン展開に関係なく) クラスのメソッドは、EXE と DLL のインスタンス化に静的なデータの相違点がある型を使用できません。

仮想関数を持つクラスを定義する DLL を定義することで、クラスのエクスポートを避けることができます。また、を呼び出して、型のオブジェクトをインスタンス化および削除することもできます。  その後、型に対して仮想関数を呼び出すことができます。

C++ 標準ライブラリの型から派生し、デバッグリリース (**/MTd**) をコンパイルし、コンパイラのエラーメッセージが参照する場合は、Visual C++ で C4275 を無視でき `_Container_base` ます。

```cpp
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```
