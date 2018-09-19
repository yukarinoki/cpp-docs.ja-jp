---
title: リソース コンパイラの警告 RW4004 |Microsoft Docs
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
ms.openlocfilehash: 33305f1f86c0cc1722e4a235ec27927f6e70675f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095990"
---
# <a name="resource-compiler-warning-rw4004"></a>リソース コンパイラの警告 RW4004

仮想キー コードに相当しない ASCII 文字

VIRTKEY 型アクセラレータの仮想キー コードに文字列リテラルが使用されました。

この警告では、処理を続行できますが、生成されたアクセラレータ キーが指定した文字列と一致しない可能性があることに注意してください。 (VIRTKEY は、ASCII アクセラレータとは異なるキー コードを使用します。)

使用して、アクセラレータを入手することを確認する文字列リテラルは構文的に有効ですが、のみできます、 **vk _\* #define** WINDOWS.h の値。