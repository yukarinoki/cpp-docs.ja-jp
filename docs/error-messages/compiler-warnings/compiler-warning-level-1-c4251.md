---
title: コンパイラの警告 (レベル 1) C4251 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d964c375adf80caef3bb5a6eb06c67ef8e3e7200
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890050"
---
# <a name="compiler-warning-level-1-c4251"></a>コンパイラの警告 (レベル 1) C4251

'identifier': クラス 'type' を 'type2' のクラスのクライアントで使用される dll のインターフェイスを持っている必要があります

持つクラスをエクスポートするときに、データ破損の可能性を最小限に抑える[方式](../../cpp/dllexport-dllimport.md)、いることを確認します。

- すべての静的データは、DLL からエクスポートされた関数を使用してアクセスします。

- クラスのインライン メソッドは静的データを変更できません。

- クラスのメソッドがインライン展開が CRT 関数を使用しないまたはその他のライブラリ関数を使用して、静的データ (を参照してください[潜在的なエラーを渡す境界を越えて CRT オブジェクト DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)詳細については)。

- クラスのメソッドがありません (に関係なくインライン展開) EXE および DLL でインスタンス化の静的データの相違点のある型を使用できます。

クラスのインスタンスを作成する仮想関数を持つクラスを定義し、機能する DLL を呼び出すことができますを定義して、型のオブジェクトを削除してエクスポートを回避できます。  仮想関数を型でだけ呼び出すことができます、します。

デバッグのリリースをコンパイルする C++ 標準ライブラリ内の型から派生した場合に無視できる C4251 (**/MTd**)、コンパイラのエラー メッセージは _Container_base を指します。

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```