---
title: NMAKE の致命的なエラー U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: c963180059a48d9aa0b09103df1ed54f82b8a2f1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193395"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE の致命的なエラー U1099

スタック オーバーフロー

処理中のメイクファイルは、NMAKE の現在のスタック割り当てに対して複雑すぎました。 NMAKE には 0x3000 (12K) の割り当てがあります。

NMAKE のスタック割り当てを増やすには、より大きなスタックオプションを使用して[editbin/stack](../../build/reference/stack.md)ユーティリティを実行します。

**editbin/STACK: NMAKE を予約します。EXCEL.EXE**

ここで、 *reserve*は NMAKE の現在のスタック割り当てよりも大きい数値です。
