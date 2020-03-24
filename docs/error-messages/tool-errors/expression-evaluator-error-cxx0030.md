---
title: 式エバリュエーター エラー CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: 477ec31d18924e91baf2d8b7b732bc7a50eee53b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195618"
---
# <a name="expression-evaluator-error-cxx0030"></a>式エバリュエーター エラー CXX0030

式が評価可能ではありません

デバッガーの式エバリュエーターは、記述された式の値を取得できませんでした。 考えられる原因の1つは、式がプログラムのアドレス空間の外部にあるメモリを参照する (null ポインターの逆参照が1つの例) ことです。 Windows では、プログラムのアドレス空間の外部にあるメモリにアクセスすることはできません。

かっこを使用して式を書き直し、評価の順序を制御することもできます。

このエラーは CAN0030 と同じです。
