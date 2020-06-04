---
title: コンパイラの警告 (レベル 1) C4251
ms.date: 04/21/2020
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 9f261d3deb7f1cac8cd5c60b920e0be49bc8b7a6
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032331"
---
# <a name="compiler-warning-level-1-c4251"></a>コンパイラの警告 (レベル 1) C4251

> '*型*' : クラス ' 型 1 ' は、 '*type2*' クラスのクライアントが使用する dll インターフェイスを持っている必要があります。*type1*

## <a name="remarks"></a>解説

[__declspec(dllexport)](../../cpp/dllexport-dllimport.md)として宣言されたクラスをエクスポートする際にデータが破損する可能性を最小限に抑えるには、次の手順を実行します。

- すべての静的データは、DLL からエクスポートされた関数を通じてアクセスされます。

- クラスのインライン メソッドでは、静的データを変更できません。

- クラスのインライン メソッドは、CRT 関数や静的データを使用する他のライブラリ関数を使用しません。 詳細については、「 [DLL 境界を越えて CRT オブジェクトを渡す場合の潜在的なエラー](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)」を参照してください。

- EXE と DLL のインスタンス化に静的なデータの違いがある型を使用することはできません (インラインかどうかに関係なく) クラスのメソッドは使用できません。

DLL からクラスをエクスポートする際の問題を回避できます: 仮想関数を持つクラスを定義し、その型のオブジェクトをインスタンス化および削除する関数を定義します。 その後、型の仮想関数を呼び出すだけです。

C4251 は、クラスが C++ 標準ライブラリの型から派生していて、デバッグ リリース (**/MTd**) をコンパイルしていて、コンパイラ のエラー メッセージが`_Container_base`参照している場合は無視できます。

## <a name="example"></a>例

このサンプルでは、 から派生`VecWrapper`した特殊`std::vector`なクラスをエクスポートします。

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllexport) VecWrapper : vector<Node *> {};   // C4251
```
