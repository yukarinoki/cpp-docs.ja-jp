---
title: 式エバリュエーター エラー CXX0024
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: 525210090b0a4c2966f2e1432f85fd4bb6a8156d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195761"
---
# <a name="expression-evaluator-error-cxx0024"></a>式エバリュエーター エラー CXX0024

操作には左辺値が必要です

左辺値を必要とする演算に対して、左辺値に評価されない式が指定されました。

左辺値 (この場合、代入ステートメントの左側にが表示されるために呼び出される) は、メモリ位置を参照する式です。

たとえば、`buffer[count]` は特定のメモリ位置を指しているため、有効な左辺値です。 論理比較 `zed != 0` は、メモリアドレスではなく TRUE または FALSE と評価されるため、有効な左辺値ではありません。

このエラーは CAN0024 と同じです。
