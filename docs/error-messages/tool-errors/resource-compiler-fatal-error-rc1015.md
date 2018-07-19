---
title: リソース コンパイラの致命的なエラー RC1015 |Microsoft ドキュメント
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
ms.openlocfilehash: b7744242e44ecfc72ee57ab979969ad81b209e57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322823"
---
# <a name="resource-compiler-fatal-error-rc1015"></a>リソース コンパイラの致命的なエラー RC1015
インクルード ファイル 'filename' を開くことはできません。  
  
 指定したインクルード ファイルが存在しませんを開けませんでした、またはが見つかりませんでした。  
  
 環境設定が有効であることと、ファイルの正しいパスを指定していることを確認してください。 十分なファイル ハンドルが、リソース コンパイラで使用できることを確認します。 ネットワーク ドライブにファイルがある場合は、ファイルを開く権限があることを確認します。  
  
 -> リソースの構成のプロパティで追加のインクルード ディレクトリとして指定されたディレクトリにインクルード ファイルが存在する場合でも、RC1015 が発生する可能性が -> [全般] プロパティ ページインクルード ファイルを完全なパスを指定します。  
  
 詳細については、サポート技術情報の記事 Q326987 を参照してください: RC1015 エラーときに使用する場合にリソース ビュー インクルード パスが長すぎます。