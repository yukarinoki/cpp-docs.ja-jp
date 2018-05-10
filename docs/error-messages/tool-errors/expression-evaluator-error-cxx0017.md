---
title: 式エバリュエーター エラー CXX0017 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0017
dev_langs:
- C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7540dc701ffa6e0acb3d2661e1196e5f4552d2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0017"></a>式エバリュエーター エラー CXX0017
シンボルが見つかりません  
  
 式で指定されたシンボルが見つかりませんでした。  
  
 このエラーの考えられる原因の 1 つは、シンボル名の大文字が一致しません。 C および C++ 言語を区別するため、正確な場合は、ソースで定義されているシンボル名を指定してください。  
  
 このエラーは、デバッグ中に変数を監視するために変数をキャストしようとしているときに発生することができます。 `typedef`型の新しい名前を宣言して新しい型が定義されていません。 型キャスト、デバッガーで試行すると、定義済みの型の名前が必要です。  
  
 このエラーは、can0017 と同じものと同じです。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  シンボルは既に宣言されてが使用されているプログラム内の位置を確認します。  
  
2.  デバッガーで変数をキャストする実際の型名を使用してではなく、`typedef`の名前を定義します。