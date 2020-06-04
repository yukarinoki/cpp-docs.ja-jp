---
title: NMAKE の致命的なエラー U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: 9c6b939c97f993e42049677292374377d825d474
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193681"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE の致命的なエラー U1051

メモリが不足しています

メイクファイルが大きすぎるか複雑すぎるため、NMAKE で仮想メモリなどのメモリが不足していました。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. ディスク上の空き領域を増やします。

1. Windows NT ページングファイルまたは Windows スワップファイルのサイズを大きくします。

1. メイクファイルの一部だけが使用されている場合は、makefile を別のファイルに分割するか、を使用します **。** プリプロセスディレクティブで、NMAKE が処理する必要がある量を制限する場合は。 **!ディレクティブに** **!の場合**、`!IFDEF`、 **!IFNDEF**、 **!それ以外の場合は**、 **!それ以外**の `IFDEF`、および **!それ以外**の場合は `IFNDEF`。
