---
title: リソース コンパイラの警告 RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: ca0fb271a5ab43994ec37cc8d59c33877903f6e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182345"
---
# <a name="resource-compiler-warning-rw4004"></a>リソース コンパイラの警告 RW4004

仮想キー コードに相当しない ASCII 文字

VIRTKEY 型アクセラレータの仮想キー コードに文字列リテラルが使用されました。

この警告では、処理を続行できますが、生成されたアクセラレータ キーが指定した文字列と一致しない可能性があることに注意してください。 (VIRTKEY は、ASCII アクセラレータとは異なるキー コードを使用します。)

文字列リテラルは構文的には有効ですが、必要なアクセラレータを取得できるのは、WINDOWS .h の**VK_\* #define**値を使用した場合のみです。
