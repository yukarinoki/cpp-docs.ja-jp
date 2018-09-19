---
title: NMAKE の致命的なエラー U1051 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3d3a14b75a30aa22bcc9faafb97a218051bb080
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045017"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE の致命的なエラー U1051

メモリ不足

NMAKE は、メイクファイルが大きすぎるか複雑なために、仮想メモリを含む、メモリが不足します。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ディスク領域を解放します。

1. Windows NT のページング ファイルまたは Windows のスワップ ファイルのサイズを増やします。

1. メイクファイルの一部を使用している場合のみ、メイクファイルを個別のファイルに分割またはのいずれかを使用して、 **!IF**プリプロセス ディレクティブ (nmake の) を処理する必要がある量を制限します。 **!IF**ディレクティブには、 **!IF**、 `!IFDEF`、 **!IFNDEF**、 **!ELSE IF**、 **!ELSE** `IFDEF`、および **!ELSE** `IFNDEF`します。