---
title: 式エバリュエーター エラー CXX0033
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 2916808d98f1fabc2157fbedc96d76e196661279
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195514"
---
# <a name="expression-evaluator-error-cxx0033"></a>式エバリュエーター エラー CXX0033

OMF 型情報にエラーがあります

実行可能ファイルに、デバッグ用の有効なオブジェクトモジュール形式 (OMF) がありませんでした。

このエラーは CAN0033 と同じです。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. このバージョンのビジュアルC++と共にリリースされたリンカーを使用して、実行可能ファイルが作成されませんでした。 現在のバージョンの setup.exe を使用して、オブジェクトコードを再度リンクします。

1. .Exe ファイルが破損している可能性があります。 プログラムを再コンパイルして再リンクします。
