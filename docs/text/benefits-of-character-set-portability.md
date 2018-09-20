---
title: 利点がありますの文字のセットにおける移植性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 115a4524f3b11d847291015f3bee5ca10f628310
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423443"
---
# <a name="benefits-of-character-set-portability"></a>文字セットにおける移植性の利点

現在しないアプリケーションを国際化する場合でも、MFC および C ランタイムの移植性の機能を使用して得ることができます。

- 柔軟な基本コードは、移植可能な方法でコーディングします。 後で移動できます簡単に Unicode や MBCS にします。

- 効率的な Windows のアプリケーションは、Unicode を使用します。 Windows では、Unicode を使用するため、オペレーティング システムとの間に渡される Unicode 以外の文字列変換される必要が、オーバーヘッドが発生します。


## <a name="see-also"></a>関連項目

[Unicode と MBCS](../text/unicode-and-mbcs.md)<br/>
[Unicode のサポート](../text/support-for-unicode.md)