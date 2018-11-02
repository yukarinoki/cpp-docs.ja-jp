---
title: リンカ ツール エラー LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: 69ac20522aebb7391319c0de210e06b305f3fd0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461257"
---
# <a name="linker-tools-error-lnk1188"></a>リンカ ツール エラー LNK1188

BADFIXUPSECTION:: 無効な fixup ターゲット 'symbol';可能なセクションの長さは 0

VxD リンク中に再配置のターゲットは、セクションがありませんでした。 Link386 (以前のバージョン)、0 長セクションには、0 以外の長さがもう 1 つのセクションを結合に (グループの MASM ディレクティブによって生成される)、OMF グループ レコードが使用されている可能性があります。 COFF 形式は、長さ 0 のセクションでは、グループ ディレクティブをサポートしていません。 リンクは、COFF に自動的にこの種類の OMF オブジェクトを変換、このエラーが発生する可能性があります。