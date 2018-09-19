---
title: リンカ ツール エラー LNK1188 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36b31590d94d809c16ed64d16071db0919f60238
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098941"
---
# <a name="linker-tools-error-lnk1188"></a>リンカ ツール エラー LNK1188

BADFIXUPSECTION:: 無効な fixup ターゲット 'symbol';可能なセクションの長さは 0

VxD リンク中に再配置のターゲットは、セクションがありませんでした。 Link386 (以前のバージョン)、0 長セクションには、0 以外の長さがもう 1 つのセクションを結合に (グループの MASM ディレクティブによって生成される)、OMF グループ レコードが使用されている可能性があります。 COFF 形式は、長さ 0 のセクションでは、グループ ディレクティブをサポートしていません。 リンクは、COFF に自動的にこの種類の OMF オブジェクトを変換、このエラーが発生する可能性があります。