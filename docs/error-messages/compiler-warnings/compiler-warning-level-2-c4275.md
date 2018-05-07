---
title: コンパイラの警告 (レベル 2) C4275 |Microsoft ドキュメント
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
ms.openlocfilehash: a5d2a3cd7c4b937f8bee1b8f8e37e0619cc224ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4275"></a>コンパイラの警告 (レベル 2) C4275
非 DLL インターフェイスした 'identifier' ベースとして使用される DLL インターフェイスした 'identifier' の  
  
 エクスポートされたクラスは、エクスポートされていないクラスから派生しました。  
  
 持つクラスをエクスポートするときに、データの破損の可能性を最小限に抑える[方式](../../cpp/dllexport-dllimport.md)、いることを確認します。  
  
-   すべての静的データは DLL からエクスポートされる関数を使用してアクセスします。  
  
-   クラスのメソッドをインライン展開は静的データを変更できません。  
  
-   クラスのメソッドをインライン展開が CRT 関数を使用していないか、他のライブラリ関数が静的データを使用します。  
  
-   インライン クラス関数を使用していない CRT 関数、またはその他のライブラリ関数、静的データにアクセスするなど、ここで。  
  
-   クラスのメソッドがありません (に関係なくインライン展開)、EXE および DLL にインスタンス化の静的なデータの相違点のある型を使用できます。  
  
 クラスのインスタンスを作成する仮想関数を持つクラスを定義し、関数を DLL が呼び出すことができますを定義して、型のオブジェクトを削除してエクスポートを回避できます。  仮想関数を型にのみ呼び出すことができますし、します。  
  
 テンプレートをエクスポートする方法の詳細については、次を参照してください。 [http://support.microsoft.com/default.aspx?scid=KBです。EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)です。  
  
 デバッグ リリースをコンパイルする C++ 標準ライブラリ内の型から派生した場合、Visual C で C4275 を無視することができます (**/MTd**) し、コンパイラ エラー メッセージは _Container_base を参照します。  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```