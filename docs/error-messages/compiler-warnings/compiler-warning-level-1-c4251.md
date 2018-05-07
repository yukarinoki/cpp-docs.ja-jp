---
title: コンパイラの警告 (レベル 1) C4251 |Microsoft ドキュメント
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
ms.openlocfilehash: 366d66a38685e75e47d8921f9ebd525b334ced7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4251"></a>コンパイラの警告 (レベル 1) C4251
'identifier': クラス 'type' はクラス 'type2' のクライアントで使用する dll のインターフェイスを持っている必要があります  
  
 持つクラスをエクスポートするときに、データの破損の可能性を最小限に抑える[方式](../../cpp/dllexport-dllimport.md)、いることを確認します。  
  
-   すべての静的データは、DLL からエクスポートされる関数を使用してアクセスします。  
  
-   クラスのメソッドをインライン展開は静的データを変更できません。  
  
-   クラスのメソッドをインライン展開が CRT 関数を使用しない、またはその他のライブラリ関数が静的データを使用して (を参照してください[潜在的なエラー渡す CRT オブジェクト DLL の境界を越えて](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)詳細については)。  
  
-   クラスのメソッドがありません (に関係なくインライン展開)、EXE および DLL にインスタンス化の静的なデータの相違点のある型を使用できます。  
  
 クラスのインスタンスを作成する仮想関数を持つクラスを定義し、関数を DLL が呼び出すことができますを定義して、型のオブジェクトを削除してエクスポートを回避できます。  仮想関数を型にのみ呼び出すことができますし、します。  
  
 テンプレートをエクスポートする方法の詳細については、次を参照してください。 [http://support.microsoft.com/default.aspx?scid=KBです。EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)です。  
  
 デバッグ、リリースをコンパイルする C++ 標準ライブラリ内の型から派生した場合、C4251 を無視することができます (**/MTd**) し、コンパイラ エラー メッセージは _Container_base を参照します。  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```