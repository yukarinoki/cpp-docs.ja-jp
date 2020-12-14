---
description: 詳細については、「式エバリュエーターエラー CXX0015」を参照してください。
title: 式エバリュエーター エラー CXX0015
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: c5d6e0ba5407646b1e3c835053f1f115dabf4fe7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228327"
---
# <a name="expression-evaluator-error-cxx0015"></a>式エバリュエーター エラー CXX0015

式が複雑すぎます (スタックオーバーフロー)

入力した式が複雑すぎるか、C 式エバリュエーターで使用できるストレージの量に対して深すぎます。

オーバーフローは通常、保留中の計算の数が多すぎることが原因で発生します。

式の他の部分が計算されるまで待機するのではなく、式の各要素が検出されたときに評価できるように、式を再配置します。

式を複数のコマンドに分割します。

このエラーは CAN0015 と同じです。
