---
title: コンパイラ エラー C2567 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05f89362f36a6ba576e9829153f0d8931c4975c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229690"
---
# <a name="compiler-error-c2567"></a>コンパイラ エラー C2567
'file' のメタデータを開くことができません、ファイルが削除されたか移動  
  
 ソースの参照されたメタデータ ファイル (で`#using`) が見つかりませんでした同じディレクトリに、コンパイラ バックエンド プロセスによってコンパイラ フロント エンドのプロセスによってだとします。 参照してください[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)詳細についてはします。  
  
 コンパイルする場合は、C2567 を原因となったでした **/c** 1 つでコンピューターし、その後、別のコンピューター上のリンク時コード生成を試みます。 詳細については、次を参照してください。 [/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md))。  
  
 お使いのコンピューターがメモリ不足であることを示すも可能性があります。  
  
 このエラーを解決するには、ビルド プロセスのすべてのフェーズの同じディレクトリの場所にメタデータ ファイルであることを確認します。