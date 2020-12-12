---
description: 詳細については、「CVTRES Fatal Error CVT1100」を参照してください。
title: CVTRES の致命的なエラー CVT1100
ms.date: 11/04/2016
f1_keywords:
- CVT1100
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
ms.openlocfilehash: e54a3aeaf8b0b7955ab7e9cb7558c97a57fc95e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119737"
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES の致命的なエラー CVT1100

重複したリソース—種類、名前: 名前、言語: 言語、フラグ: フラグ、サイズ: サイズ

指定されたリソースが複数回指定されました。

リンカーがタイプライブラリを作成していて、 [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) を指定せず、プロジェクト内のリソースが既に1を使用している場合、このエラーが発生することがあります。 この場合は、/TLBID を指定し、65535までの別の番号を指定します。
