---
description: 詳細については、「NMAKE の致命的なエラー U1099」を参照してください。
title: NMAKE の致命的なエラー U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: 8044010cf967e4fe27b2235968022023d66ae1c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345317"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE の致命的なエラー U1099

スタック オーバーフロー

処理中のメイクファイルは、NMAKE の現在のスタック割り当てに対して複雑すぎました。 NMAKE には 0x3000 (12K) の割り当てがあります。

NMAKE のスタック割り当てを増やすには、より大きなスタックオプションを使用して [editbin/stack](../../build/reference/stack.md) ユーティリティを実行します。

**editbin/STACK: 予約 NMAKE.EXE**

ここで、 *reserve* は NMAKE の現在のスタック割り当てよりも大きい数値です。
