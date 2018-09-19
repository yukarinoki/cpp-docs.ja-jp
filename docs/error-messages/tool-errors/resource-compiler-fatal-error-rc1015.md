---
title: リソース コンパイラの致命的なエラー RC1015 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1015
dev_langs:
- C++
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a72cba53ebe9a286ac2e7cbbf2c41b78f4e4e08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100767"
---
# <a name="resource-compiler-fatal-error-rc1015"></a>リソース コンパイラの致命的なエラー RC1015

インクルード ファイル 'filename' を開くことはできません。

指定したインクルード ファイルが存在しないかを開けませんでしたが見つかりませんでした。

環境設定が有効であることと、ファイルの正しいパスを指定していることを確認してください。 十分なファイル ハンドルがリソース コンパイラを使用できることを確認します。 ファイルがネットワーク ドライブ上にある場合は、ファイルを開く権限があることを確認します。

-> リソースの構成のプロパティで追加のインクルード ディレクトリとして指定されたディレクトリのインクルード ファイルが存在する場合でも、RC1015 が発生することが [全般] プロパティ ページ ->インクルード ファイルへの完全パスを指定します。

詳細については、サポート技術情報記事 Q326987 を参照してください: RC1015 エラーときに使用する場合にリソース ビュー インクルード パスが長すぎます。