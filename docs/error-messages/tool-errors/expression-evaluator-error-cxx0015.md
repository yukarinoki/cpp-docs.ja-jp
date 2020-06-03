---
title: 式エバリュエーター エラー CXX0015
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: 19cf47d6b7b718eb19b987bcc16854af3266069b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196067"
---
# <a name="expression-evaluator-error-cxx0015"></a>式エバリュエーター エラー CXX0015

式が複雑すぎます (スタックオーバーフロー)

入力した式が複雑すぎるか、C 式エバリュエーターで使用できるストレージの量に対して深すぎます。

オーバーフローは通常、保留中の計算の数が多すぎることが原因で発生します。

式の他の部分が計算されるまで待機するのではなく、式の各要素が検出されたときに評価できるように、式を再配置します。

式を複数のコマンドに分割します。

このエラーは CAN0015 と同じです。
