---
description: '詳細情報: コンパイラの警告 (レベル 4) C4960'
title: コンパイラの警告 (レベル 4) C4960
ms.date: 11/04/2016
f1_keywords:
- C4960
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
ms.openlocfilehash: 9a1e3d5390ffa4ffad101d1ea2c3164c04d12ca8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234580"
---
# <a name="compiler-warning-level-4-c4960"></a>コンパイラの警告 (レベル 4) C4960

'function' はプロファイルするには多き過ぎます

[/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)を使用するときに、命令が 65,535 を超える関数を含む入力モジュールが検出されました。 このような大きい関数は、ガイド付き最適化のプロファイルに使用できません。

この警告を解決するには、関数のサイズを小さくします。
