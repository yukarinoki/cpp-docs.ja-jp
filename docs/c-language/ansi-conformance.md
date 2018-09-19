---
title: ANSI 規格適合性 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ANSI [C++]
- ANSI [C++], C standard
ms.assetid: c3a188c8-42bc-41fb-a78d-637f3175ade0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cca68ad9865ab6382114c3ebe64d5921539f7ce0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106884"
---
# <a name="ansi-conformance"></a>ANSI 規格適合性

Microsoft C は、ANSI C 規格の 9899:1990 エディションで定められている C 言語の規格に準拠します。

ANSI C 規格に対する Microsoft の拡張機能については、このブックのテキストと構文、およびオンライン参照で説明します。 拡張機能が ANSI C 規格の一部ではないため、それらの使用によってシステム間のプログラムの移植性が制限される場合があります。 既定では、Microsoft 拡張機能は有効になっています。 拡張機能を無効にするには、/Za コンパイラ オプションを指定します。 /Za では、すべての非 ANSI コードがエラーまたは警告を生成します。

## <a name="see-also"></a>参照

[『C 言語リファレンス』の構成](../c-language/organization-of-the-c-language-reference.md)