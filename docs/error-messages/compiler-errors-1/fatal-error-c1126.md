---
title: 致命的なエラー C1126 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f014aafc60a36bfbb4edad50e7e3ceede6e3c8b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062476"
---
# <a name="fatal-error-c1126"></a>致命的なエラー C1126

'identifier': 自動メモリ割り当てサイズを超えています

関数 (とスワップ可能な関数の追加の 20 バイトなど、コンパイラによって使用される領域量が制限されています) のローカル変数に割り当てられた領域を超えています。

このエラーを修正するには使用`malloc`または`new`大量のデータを割り当てることです。