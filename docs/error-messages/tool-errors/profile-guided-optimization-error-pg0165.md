---
title: プロファイル ガイド付き最適化のエラー PG0165 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acad97411480112d06dadd454d1368dcfdf2c87f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318416"
---
# <a name="profile-guided-optimization-error-pg0165"></a>ガイド付き最適化のプロファイルのエラー PG0165
'Filename.pgd' を読み込んでいます: ' PGD バージョンがサポートされていません (バージョンの不一致)' です。  
  
 PGD ファイルは、特定のコンパイラ ツールセットを特定します。 別のコンパイラを使用するものを使用しているときにこのエラーは生成*Filename*.pgd です。 このエラーは、このコンパイラ ツールセットがからデータを使用できないことを示して*Filename*.pgd を現在のプログラムを最適化します。  
  
 この問題を解決するには、再生成*Filename*.pgd 現在コンパイラ ツールセットを使用しています。