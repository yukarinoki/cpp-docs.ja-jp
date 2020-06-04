---
title: リンカ ツール エラー LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: b18a93c7434ee3d66f42829f373bd916a65369bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195176"
---
# <a name="linker-tools-error-lnk1188"></a>リンカ ツール エラー LNK1188

BADFIXUPSECTION:: 無効な fixup ターゲット ' symbol ';使用可能な長さゼロのセクション

VxD リンク中に、再配置のターゲットにセクションがありませんでした。 LINK386 (古いバージョン) では、(MASM グループディレクティブによって生成される) OMF グループレコードを使用して、ゼロの長さのセクションと0以外の長さのセクションを結合することができます。 COFF 形式では、GROUP ディレクティブと長さ0のセクションはサポートされません。 LINK がこの種類の OMF オブジェクトを COFF に自動的に変換する場合、このエラーが発生することがあります。
