---
description: 詳細については、「リソースコンパイラの警告 RW4004」を参照してください。
title: リソース コンパイラの警告 RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: 5609d49e242ba7d74025622c53c279ae1b0da854
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236998"
---
# <a name="resource-compiler-warning-rw4004"></a>リソース コンパイラの警告 RW4004

仮想キー コードに相当しない ASCII 文字

VIRTKEY 型アクセラレータの仮想キー コードに文字列リテラルが使用されました。

この警告では、処理を続行できますが、生成されたアクセラレータ キーが指定した文字列と一致しない可能性があることに注意してください。 (VIRTKEY は、ASCII アクセラレータとは異なるキー コードを使用します。)

文字列リテラルは構文的には有効ですが、必要なアクセラレータを取得できるのは、WINDOWS .h の **VK_ \* #define** 値を使用することだけです。
