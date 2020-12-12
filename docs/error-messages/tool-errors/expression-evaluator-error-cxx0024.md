---
description: 詳細については、「式エバリュエーターエラー CXX0024」を参照してください。
title: 式エバリュエーター エラー CXX0024
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: cb40199c217180b08e62d89dee551130eefefc35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228080"
---
# <a name="expression-evaluator-error-cxx0024"></a>式エバリュエーター エラー CXX0024

操作には左辺値が必要です

左辺値を必要とする演算に対して、左辺値に評価されない式が指定されました。

左辺値 (この場合、代入ステートメントの左側にが表示されるために呼び出される) は、メモリ位置を参照する式です。

たとえば、 `buffer[count]` は、特定のメモリ位置を指しているため、有効な左辺値です。 論理比較 `zed != 0` は、メモリアドレスではなく TRUE または FALSE と評価されるため、有効な左辺値ではありません。

このエラーは CAN0024 と同じです。
