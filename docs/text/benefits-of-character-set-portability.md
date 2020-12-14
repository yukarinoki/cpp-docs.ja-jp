---
description: '詳細情報: 文字セットの移植性の利点'
title: 文字セットにおける移植性の利点
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 32d78e6a230d664970e819f766d70beb1df52a88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187625"
---
# <a name="benefits-of-character-set-portability"></a>文字セットにおける移植性の利点

現在、アプリケーションを国際化する予定がない場合でも、MFC および C ランタイムの移植性の機能を使用すると、次のような利点があります。

- コーディング移植を使用すると、コードベースの柔軟性が向上します。 後で、Unicode または MBCS に簡単に移動できます。

- Unicode を使用すると、アプリケーションはより効率的になります。 Windows では Unicode を使用するため、オペレーティングシステムとの間でやり取りされる Unicode 以外の文字列は変換する必要があります。これにより、オーバーヘッドが発生します。

## <a name="see-also"></a>関連項目

[Unicode と MBCS](../text/unicode-and-mbcs.md)<br/>
[Unicode のサポート](../text/support-for-unicode.md)
