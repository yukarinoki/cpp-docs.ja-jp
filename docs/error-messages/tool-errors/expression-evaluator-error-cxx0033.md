---
title: 式エバリュエーター エラー CXX0033 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f37b53c30d36a43d339132bfd9baca3e5ec70c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057199"
---
# <a name="expression-evaluator-error-cxx0033"></a>式エバリュエーター エラー CXX0033

OMF の種類の情報でのエラー

実行可能ファイルには、デバッグの有効なオブジェクト モジュール形式 (OMF) がありませんでした。

このエラーは、can0033 と同じものと同じです。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 実行可能ファイルは、このバージョンの Visual C リンカーによって作成されませんでした。 LINK.exe の現在のバージョンを使用してオブジェクト コードを再リンクします。

1. .Exe ファイルが壊れている可能性があります。 再コンパイルし、プログラムを再リンクします。