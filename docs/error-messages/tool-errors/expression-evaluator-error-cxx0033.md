---
description: 詳細については、「式エバリュエーターエラー CXX0033」を参照してください。
title: 式エバリュエーター エラー CXX0033
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 714499d8d1bc0812395576fe27be690997982065
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160325"
---
# <a name="expression-evaluator-error-cxx0033"></a>式エバリュエーター エラー CXX0033

OMF 型情報にエラーがあります

実行可能ファイルに、デバッグ用の有効なオブジェクトモジュール形式 (OMF) がありませんでした。

このエラーは CAN0033 と同じです。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. このバージョンの Visual C++ でリリースされたリンカーで実行可能ファイルが作成されませんでした。 現在のバージョンの LINK.exe を使用して、オブジェクトコードを再リンクします。

1. .Exe ファイルが破損している可能性があります。 プログラムを再コンパイルして再リンクします。
