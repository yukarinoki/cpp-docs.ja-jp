---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 17edea122afc03a8c3a2fdc86ee6c06c2ccf3c85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398488"
---
# <a name="dosseg-32-bit-masm"></a>..DOSSEG (32 ビット MASM)

は、CODE first、DGROUP に含まれていないセグメント、および DGROUP 内のセグメントという MS-DOS セグメント規則に従ってセグメントを並べ替えます。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> **.DOSSEG**

## <a name="remarks"></a>コメント

DGROUP 内のセグメントは、BSS または STACK にないセグメント、BSS セグメント、および最後のスタックセグメントの順に続きます。 MASM のスタンドアロンプログラムでは、主に CodeView サポートを確保するために使用されます。 [.Dosseg](../../assembler/masm/dosseg.md)と同じです。

## <a name="see-also"></a>参照

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)
