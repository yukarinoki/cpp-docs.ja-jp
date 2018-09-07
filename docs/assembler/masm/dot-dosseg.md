---
title: .DOSSEG | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33ee0b0b049ece65786c4d4857c2e082a067fee4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693233"
---
# <a name="dosseg"></a>.DOSSEG

MS-DOS セグメントの規則に従ってセグメント: コードが最初に、タではなく、セグメントし、タにセグメントします。

## <a name="syntax"></a>構文

> .DOSSEG

## <a name="remarks"></a>Remarks

タ内のセグメントがこの順序に従います: BSS やスタックではなくセグメント、BSS のセグメントと最後にスタック セグメント。 MASM のスタンドアロン プログラムでの CodeView のサポートを確保するため、主に使用します。 同じ[DOSSEG](../../assembler/masm/dosseg.md)します。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>