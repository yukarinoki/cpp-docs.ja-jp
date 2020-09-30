---
title: ANSI C 準拠
description: ANSI C 準拠のための Microsoft C ランタイムの名前付け規則の概要について説明します。
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Ansi
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
ms.openlocfilehash: 39a3f9299be7dbef4783faa8e6d08fe6ad8461f5
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590304"
---
# <a name="ansi-c-compliance"></a>ANSI C 準拠

ランタイム システムのすべての Microsoft 固有の識別子 (関数、マクロ、定数、変数、型の定義など) の名前付け規則は、ANSI に準拠しています。 このドキュメントでは、ANSI/ISO C 標準に従うランタイム関数は、いずれも ANSI 互換であることが記載されています。 ANSI 準拠アプリケーションでは、これらの ANSI 互換の関数だけを使用してください。

Microsoft 固有の関数とグローバル変数の名前は、1 つのアンダースコアで始まります。 これらの名前は、ローカルでのみ、コードのスコープ内でオーバーライドできます。 たとえば、Microsoft ランタイム ヘッダー ファイルをインクルードするとき、`_open` という名前の Microsoft 固有の関数を、同じ名前のローカル変数を宣言することでオーバーライドできます。 ただし、独自のグローバル関数またはグローバル変数としてこの名前を使用することはできません。

Microsoft 固有のマクロとマニフェスト定数の名前は、2 つのアンダー スコア、または先頭の 1 つのアンダースコアとその直後の大文字で始まります。 これらの識別子のスコープは絶対です。 たとえば、この理由から Microsoft 固有の識別子 **_UPPER** を使用することはできません。

## <a name="see-also"></a>関連項目

[互換性](../c-runtime-library/compatibility.md)
