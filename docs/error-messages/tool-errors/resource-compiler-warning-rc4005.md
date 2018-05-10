---
title: リソース コンパイラの警告 RC4005 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 724764e443d4ab999c1df1247e9f5572ebdb2078
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-warning-rc4005"></a>リソース コンパイラの警告 RC4005
'identifier': 再定義はマクロ  
  
 識別子が 2 回定義されています。 コンパイラは、2 番目のマクロ定義を使用します。  
  
 この警告は、コマンドラインで、コードでは、マクロを定義することによって生じること、`#define`ディレクティブです。 これにはインクルード ファイルからインポートされたマクロで発生することできます。  
  
 警告をなくすため、削除するいずれかの定義かを使用して、`#undef`ディレクティブを 2 つ目の定義の前にします。