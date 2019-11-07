---
title: .REPEAT
ms.date: 11/05/2019
f1_keywords:
- .REPEAT
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
ms.openlocfilehash: 0533397c60c83f22b10c84ec72aa6eb65a71e4c0
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703564"
---
# <a name="repeat-32-bit-masm"></a>.繰り返し (32 ビット MASM)

`condition` が true になるまで*ステートメント*ブロックの実行を繰り返すコードを生成します。 [.](../../assembler/masm/dot-untilcxz.md)CX がゼロの場合は、CXZ を使用して、に置き換えることができ[ます。まで](../../assembler/masm/dot-until.md)。 `condition` は、では省略可能です **。CXZ**。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> .REPEAT<br/>
> ステートメント<br/>
> .UNTIL 条件

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>