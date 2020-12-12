---
description: 詳細については、「リンカツール Error LNK1188」を参照してください。
title: リンカ ツール エラー LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: 1bd826c3734d8079b370712ae829a0d0fb1abded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321840"
---
# <a name="linker-tools-error-lnk1188"></a>リンカ ツール エラー LNK1188

BADFIXUPSECTION:: 無効な fixup ターゲット ' symbol ';使用可能な長さゼロのセクション

VxD リンク中に、再配置のターゲットにセクションがありませんでした。 LINK386 (古いバージョン) では、(MASM グループディレクティブによって生成される) OMF グループレコードを使用して、ゼロの長さのセクションと0以外の長さのセクションを結合することができます。 COFF 形式では、GROUP ディレクティブと長さ0のセクションはサポートされません。 LINK がこの種類の OMF オブジェクトを COFF に自動的に変換する場合、このエラーが発生することがあります。
