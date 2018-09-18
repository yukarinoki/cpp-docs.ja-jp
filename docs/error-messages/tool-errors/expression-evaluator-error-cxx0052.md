---
title: 式エバリュエーター エラー CXX0052 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0052
dev_langs:
- C++
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ba8fb898930ef830857773a89cd80e4c43c59c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028156"
---
# <a name="expression-evaluator-error-cxx0052"></a>式エバリュエーター エラー CXX0052

メンバー関数は存在しません

メンバー関数は、ブレークポイントとして指定されましたが、見つかりませんでした。 インライン展開されている関数にブレークポイントを設定と、このエラーが発生することができます。

使用してファイルを再コンパイル インライン展開を強制的に切断 (/Ob0) この関数にブレークポイントを設定します。

式には、定義されていない関数が呼び出されます。

このエラーは、can0052 と同じものと同じです。