---
title: 式エバリュエーター エラー CXX0025
ms.date: 11/04/2016
f1_keywords:
- CXX0025
helpviewer_keywords:
- CAN0025
- CXX0025
ms.assetid: 3e2fb541-63b3-46ac-9f93-3dadb253bcf6
ms.openlocfilehash: 5b230c10d22abef9bdb8d1fe7030552e52ca3451
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195774"
---
# <a name="expression-evaluator-error-cxx0025"></a>式エバリュエーター エラー CXX0025

演算子には構造体または共用体が必要です

`struct` または**union**型の式を受け取る演算子が、`struct` または**union**ではない式に適用されました。

クラス、構造体、または共用体の変数のコンポーネントには、完全修飾名を指定する必要があります。 コンポーネントを完全に指定せずに入力することはできません。

このエラーは CAN0025 と同じです。
