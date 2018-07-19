---
title: リソース コンパイラの警告 RW4004 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94bd1c043ac5660c5cb8fc8b2bfa1dd2f6968b55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337107"
---
# <a name="resource-compiler-warning-rw4004"></a>リソース コンパイラの警告 RW4004
仮想キー コードに相当しない ASCII 文字  
  
 VIRTKEY 型アクセラレータの仮想キー コードに文字列リテラルが使用されました。  
  
 この警告では、処理を続行できますが、生成されたアクセラレータ キーが指定した文字列と一致しない可能性があることに注意してください。 (VIRTKEY は、ASCII アクセラレータとは異なるキー コードを使用します。)  
  
 使用して、アクセラレータを取得することを確認する文字列リテラルは構文的に有効ですが、のみことができます、 **vk _\* #define** WINDOWS.h 内の値。