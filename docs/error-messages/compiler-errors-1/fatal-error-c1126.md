---
title: 致命的なエラー C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: a6c9d06cd087eb4462ae475cc1f6d64ba451887f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203644"
---
# <a name="fatal-error-c1126"></a>致命的なエラー C1126

' identifier ': 自動割り当てがサイズを超えています

関数のローカル変数に割り当てられた領域 (スワップ可能な関数の場合は、追加の20バイトなど) が制限を超えています。

このエラーを修正するには、`malloc` または `new` を使用して大量のデータを割り当てます。
