---
title: .STACK
ms.date: 11/05/2019
f1_keywords:
- .STACK
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
ms.openlocfilehash: 78c089c771e8e5a8c82905578ec2377246a44a0e
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703527"
---
# <a name="stack-32-bit-masm"></a>.スタック (32 ビット MASM)

と共に使用[します。モデル](../../assembler/masm/dot-model.md)は、(セグメント名スタックを持つ) スタックセグメントを定義します。 省略可能な `size` は、スタックのバイト数を指定します (既定値は 1024)。 `.STACK` ディレクティブは、stack ステートメントを自動的に閉じます。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> .STACK [[サイズ]]

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>