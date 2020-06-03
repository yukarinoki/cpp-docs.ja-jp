---
title: CVTRES の致命的なエラー CVT1100
ms.date: 11/04/2016
f1_keywords:
- CVT1100
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
ms.openlocfilehash: b7e67df24d41b1e8826673146fcc27fd93d143fd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196548"
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES の致命的なエラー CVT1100

重複したリソース—種類、名前: 名前、言語: 言語、フラグ: フラグ、サイズ: サイズ

指定されたリソースが複数回指定されました。

リンカーがタイプライブラリを作成していて、 [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)を指定せず、プロジェクト内のリソースが既に1を使用している場合、このエラーが発生することがあります。 この場合は、/TLBID を指定し、65535までの別の番号を指定します。
