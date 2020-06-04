---
title: 式エバリュエーター エラー CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: b4120deec3c8e7ce14e381f782904cf83a588e43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184425"
---
# <a name="expression-evaluator-error-cxx0065"></a>式エバリュエーター エラー CXX0065

変数にはスタックフレームが必要です

現在のスコープ内に存在するものの、まだ作成されていない変数が式に含まれています。

このエラーは、関数のプロローグにステップインしても、関数のスタックフレームをまだ設定していない場合、または関数の終了コードにステップインした場合に発生する可能性があります。

式を評価する前にスタックフレームが設定されるまで、プロローグコードをステップ実行します。

このエラーは CAN0065 と同じです。
