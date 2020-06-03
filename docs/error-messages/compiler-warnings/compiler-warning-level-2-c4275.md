---
title: コンパイラの警告 (レベル 2) C4275
ms.date: 02/08/2019
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: ad12c1c27006a57c8339e9dad82e4d8e1a239a6e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161998"
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

標準ライブラリの型から派生C++し、デバッグリリース (/MTd) をコンパイルし、コンパイラのエラーメッセージが `_Container_base`を参照する場合は、Visual で C4275 を無視できます。 **/MTd** C++

```cpp
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```
