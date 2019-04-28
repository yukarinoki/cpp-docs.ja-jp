---
title: .DOSSEG
ms.date: 08/30/2018
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 28b3e351030ee83693c0fec5568aacf9b4b77c27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204362"
---
# <a name="dosseg"></a>.DOSSEG

MS-DOS セグメントの規則に従ってセグメントを並べ替えます。コードは、最初に、タではなく、セグメントし、タにセグメントします。

## <a name="syntax"></a>構文

> .DOSSEG

## <a name="remarks"></a>Remarks

タ内のセグメントがこの順序に従います: BSS やスタックではなくセグメント、BSS のセグメントと最後にスタック セグメント。 MASM のスタンドアロン プログラムでの CodeView のサポートを確保するため、主に使用します。 同じ[DOSSEG](../../assembler/masm/dosseg.md)します。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>