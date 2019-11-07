---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: 853bc9cd22d866357a4cd2d695beccc3efc20acf
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703964"
---
# <a name="invoke-32-bit-masm"></a>INVOKE (32 ビット MASM)

*式*によって指定されたアドレスでプロシージャを呼び出し、言語の種類の標準の呼び出し規約に従って、スタックまたはレジスタの引数を渡します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> INVOKE*式*[[, *arguments*]]

## <a name="remarks"></a>Remarks

プロシージャに渡される各引数には、式、レジスタペア、またはアドレス式 (`ADDR`の前にある式) を指定できます。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>