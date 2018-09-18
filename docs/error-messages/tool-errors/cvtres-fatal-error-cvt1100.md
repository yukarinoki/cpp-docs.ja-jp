---
title: CVTRES の致命的なエラー CVT1100 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CVT1100
dev_langs:
- C++
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18a5508301c54637fb34a751c8f1c4e307e47d50
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068963"
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES の致命的なエラー CVT1100

リソースが重複しています-型: 型、名前: 名前、言語の言語、フラグ: フラグ、サイズ: サイズ

特定のリソースが複数回指定されました。

リンカーがタイプ ライブラリを作成して、指定しなかった場合は、このエラーを取得できます[/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) 1 を既に使用して、プロジェクト内のリソースとします。 この場合、/TLBID を指定し、65535 までの数字を指定します。