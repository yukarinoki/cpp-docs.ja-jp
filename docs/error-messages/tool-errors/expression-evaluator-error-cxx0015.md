---
title: 式エバリュエーター エラー CXX0015 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1aa37a2cc7208063ce4cfa786de196842ab42b45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050817"
---
# <a name="expression-evaluator-error-cxx0015"></a>式エバリュエーター エラー CXX0015

式が複雑すぎます (スタック オーバーフロー)

入力された式は複雑すぎるか、C の式エバリュエーターを使用可能なストレージ量レベルが深すぎます入れ子になったでした。

通常、オーバーフローは、保留中の多数の計算のために発生します。

他の部分式を計算するを待機する必要がなくが見つかると、式の各コンポーネントを評価できるように、式のレイアウトを変更します。

複数のコマンド、式に分割します。

このエラーは、can0015 と同じものと同じです。