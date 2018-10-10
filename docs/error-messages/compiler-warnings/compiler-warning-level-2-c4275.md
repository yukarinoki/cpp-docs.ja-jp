---
title: コンパイラの警告 (レベル 2) C4275 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55b93d1ebd81850982b4f6ceac1ceb008ed1fa49
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890284"
---
# <a name="compiler-warning-level-2-c4275"></a>コンパイラの警告 (レベル 2) C4275

非 DLL インターフェイスした 'identifier' のベースとして使用した 'identifier' の DLL インターフェイス

エクスポートするクラスがエクスポートされていないクラスから派生します。

持つクラスをエクスポートするときに、データ破損の可能性を最小限に抑える[方式](../../cpp/dllexport-dllimport.md)、いることを確認します。

- すべての静的データは、DLL からエクスポートされた関数を使用してアクセスします。

- クラスのインライン メソッドは静的データを変更できません。

- クラスのメソッドがインライン展開が CRT 関数を使用しないか、他のライブラリ関数が静的データを使用します。

- クラスのインライン関数を使用していない CRT 関数、またはその他のライブラリ関数では、静的データにアクセスする例では、ここで。

- クラスのメソッドがありません (に関係なくインライン展開) EXE および DLL でインスタンス化の静的データの相違点のある型を使用できます。

クラスのインスタンスを作成する仮想関数を持つクラスを定義し、機能する DLL を呼び出すことができますを定義して、型のオブジェクトを削除してエクスポートを回避できます。  仮想関数を型でだけ呼び出すことができます、します。

デバッグのリリースをコンパイルする C++ 標準ライブラリ内の型から派生する場合は、Visual C で C4275 を無視できます (**/MTd**)、コンパイラのエラー メッセージは _Container_base を指します。

```
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```