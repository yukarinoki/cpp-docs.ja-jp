---
description: 詳細については、「式エバリュエーターエラー CXX0030」を参照してください。
title: 式エバリュエーター エラー CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: d9679d260ce81c2cb9bb8be4c082ffe8c1cfc6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237428"
---
# <a name="expression-evaluator-error-cxx0030"></a>式エバリュエーター エラー CXX0030

式が評価可能ではありません

デバッガーの式エバリュエーターは、記述された式の値を取得できませんでした。 考えられる原因の1つは、式がプログラムのアドレス空間の外部にあるメモリを参照する (null ポインターの逆参照が1つの例) ことです。 Windows では、プログラムのアドレス空間の外部にあるメモリにアクセスすることはできません。

かっこを使用して式を書き直し、評価の順序を制御することもできます。

このエラーは CAN0030 と同じです。
