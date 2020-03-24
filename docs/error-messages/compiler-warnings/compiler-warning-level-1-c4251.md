---
title: コンパイラの警告 (レベル 1) C4251
ms.date: 11/04/2016
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 8a723b7ce7fc79fb6be9c9dd2b500631098622b0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163220"
---
# <a name="compiler-warning-level-1-c4251"></a>コンパイラの警告 (レベル 1) C4251

' identifier ': クラス ' type ' は、クラス ' ' ' のクライアントで使用される dll インターフェイスを持つ必要があります

[__Declspec (dllexport)](../../cpp/dllexport-dllimport.md)を使用してクラスをエクスポートする際にデータが破損する可能性を最小限に抑えるには、次の点を確認してください。

- すべての静的データは、DLL からエクスポートされた関数を介してアクセスされます。

- クラスのインラインメソッドで静的データを変更することはできません。

- クラスのインラインメソッドで CRT 関数やその他のライブラリ関数を使用しない場合は、静的データを使用します (詳細については、「 [DLL の境界を越えて Crt オブジェクトを渡すと発生する可能性のあるエラー](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) 」を参照)。

- (インライン展開に関係なく) クラスのメソッドは、EXE と DLL のインスタンス化に静的なデータの相違点がある型を使用できません。

仮想関数を持つクラスを定義する DLL を定義することで、クラスのエクスポートを避けることができます。また、を呼び出して、型のオブジェクトをインスタンス化および削除することもできます。  その後、型に対して仮想関数を呼び出すことができます。

C++標準ライブラリの型から派生し、デバッグリリース ( **/MTd**) をコンパイルして、コンパイラのエラーメッセージが _Container_base を参照する場合は、C4251 を無視できます。

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```
