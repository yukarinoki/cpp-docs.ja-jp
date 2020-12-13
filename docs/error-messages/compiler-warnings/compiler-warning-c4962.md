---
description: 詳細については、「コンパイラの警告 C4962」を参照してください。
title: コンパイラの警告 C4962
ms.date: 11/04/2016
f1_keywords:
- C4962
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
ms.openlocfilehash: a263f89c0b57eca07f0ab27758163052586eda03
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336066"
---
# <a name="compiler-warning-c4962"></a>コンパイラの警告 C4962

'function' : 最適化によってプロファイル データに矛盾が生じたため、ガイド付き最適化のプロファイルを無効にします。

関数のカウント (プロファイル) データの信頼性が低かったため、この関数は /LTCG:PGO を指定してコンパイルされませんでした。 その関数の信頼性の低いプロファイル データを格納している .pgc ファイルを再生成するためにプロファイリングを再実行します。

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。
