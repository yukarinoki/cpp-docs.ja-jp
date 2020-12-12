---
description: 詳細については、「NMAKE の致命的なエラー U1051」を参照してください。
title: NMAKE の致命的なエラー U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: c7d465eaf34adb69e41f523006fb0740eea722ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272111"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE の致命的なエラー U1051

メモリが不足しています

メイクファイルが大きすぎるか複雑すぎるため、NMAKE で仮想メモリなどのメモリが不足していました。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ディスク上の空き領域を増やします。

1. Windows NT ページングファイルまたは Windows スワップファイルのサイズを大きくします。

1. メイクファイルの一部だけが使用されている場合は、makefile を別のファイルに分割するか、を使用します **。** プリプロセスディレクティブで、NMAKE が処理する必要がある量を制限する場合は。 **!ディレクティブに** **!、**、 `!IFDEF` **!IFNDEF**、 **!それ以外の場合は**、 **!それ以外** `IFDEF` の場合は、 **!それ以外** `IFNDEF` の場合。
