---
title: 致命的なエラー C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: 110fbfe984ee7714e0c8ee2e2cb4deec4f43905a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207928"
---
# <a name="fatal-error-c1126"></a>致命的なエラー C1126

' identifier ': 自動割り当てがサイズを超えています

関数のローカル変数に割り当てられた領域 (スワップ可能な関数の場合は、追加の20バイトなど) が制限を超えています。

このエラーを修正するに `malloc` は、またはを使用して **`new`** 大量のデータを割り当てます。
