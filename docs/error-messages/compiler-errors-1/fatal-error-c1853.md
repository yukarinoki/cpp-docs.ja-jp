---
title: 致命的なエラー C1853 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa6a67c13f76b0bf43159b9e9de95068102a2b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229210"
---
# <a name="fatal-error-c1853"></a>致命的なエラー C1853
  
> '*filename*' プリコンパイル済みヘッダー ファイルが以前のバージョンのコンパイラでからまたはプリコンパイル済みヘッダーは、C++ および C から (またはその逆) に使用します。  
  
以下の原因が考えられます。  
  
-   プリコンパイル済みヘッダーは、旧バージョンのコンパイラでコンパイルされました。 現在のコンパイラでヘッダーを再コンパイルしてください。  
  
-   プリコンパイル済みヘッダーは、C++ および C C で使用するヘッダーからのいずれかを指定して使用している、 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション、またはソース ファイルのサフィックスの"c"に変更します。 詳細については、次を参照してください。[コードをプリコンパイルする 2 つの選択肢](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code)です。