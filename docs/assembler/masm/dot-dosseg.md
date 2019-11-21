---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 8f0388c3df9804c0cdb105162a962a44fe207345
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703316"
---
# <a name="dosseg-32-bit-masm"></a>..DOSSEG (32 ビット MASM)

は、CODE first、DGROUP に含まれていないセグメント、および DGROUP 内のセグメントという MS-DOS セグメント規則に従ってセグメントを並べ替えます。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> .DOSSEG

## <a name="remarks"></a>Remarks

DGROUP 内のセグメントは、BSS または STACK にないセグメント、BSS セグメント、および最後のスタックセグメントの順に続きます。 MASM のスタンドアロンプログラムでは、主に CodeView サポートを確保するために使用されます。 [.Dosseg](../../assembler/masm/dosseg.md)と同じです。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>