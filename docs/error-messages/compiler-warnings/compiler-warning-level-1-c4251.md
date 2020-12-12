---
description: '詳細情報: コンパイラの警告 (レベル 1) C4251'
title: コンパイラの警告 (レベル 1) C4251
ms.date: 04/21/2020
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 4d08462442fd64ebef85573f5d538d6a884c8131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266235"
---
# <a name="compiler-warning-level-1-c4251"></a>コンパイラの警告 (レベル 1) C4251

> '*type*': クラス '*type1*' は、*クラス '* type1 ' のクライアントで使用される dll インターフェイスを持つ必要があります

## <a name="remarks"></a>解説

[__Declspec (dllexport)](../../cpp/dllexport-dllimport.md)として宣言されたクラスをエクスポートする際にデータが破損する可能性を最小限に抑えるには、次の点を確認してください。

- すべての静的データには、DLL からエクスポートされた関数を介してアクセスします。

- クラスのインラインメソッドで静的データを変更することはできません。

- 静的データを使用する CRT 関数やその他のライブラリ関数は、クラスのインラインメソッドでは使用されません。 詳細については、「 [DLL の境界を越えて CRT オブジェクトを渡す可能性のあるエラー](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)」を参照してください。

- クラスのメソッド (インラインであるかどうかにかかわらず) では、EXE と DLL のインスタンス化に静的なデータの相違点がある型を使用できます。

DLL からクラスをエクスポートする際の問題を回避するには、仮想関数を使用するようにクラスを定義し、その型のオブジェクトをインスタンス化および削除する関数を定義します。 その後、型に対して仮想関数を呼び出すことができます。

C4251 は無視できます。クラスが C++ 標準ライブラリの型から派生している場合は、デバッグリリース (**/MTd**) をコンパイルし、コンパイラのエラーメッセージが参照する場所をコンパイルし `_Container_base` ます。

## <a name="example"></a>例

このサンプルでは、から派生した特殊なクラスをエクスポート `VecWrapper` `std::vector` します。

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllexport) VecWrapper : vector<Node *> {};   // C4251
```
