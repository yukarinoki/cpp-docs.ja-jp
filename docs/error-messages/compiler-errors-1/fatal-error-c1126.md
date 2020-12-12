---
description: '詳細情報: 致命的なエラー C1126'
title: 致命的なエラー C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: d6898b65bafa6862c77b10aa362ffc0a0df6e597
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181008"
---
# <a name="fatal-error-c1126"></a>致命的なエラー C1126

' identifier ': 自動割り当てがサイズを超えています

関数のローカル変数に割り当てられた領域 (スワップ可能な関数の場合は、追加の20バイトなど) が制限を超えています。

このエラーを修正するに `malloc` は、またはを使用して **`new`** 大量のデータを割り当てます。
