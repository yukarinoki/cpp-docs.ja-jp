---
title: プロジェクト ビルド エラー PRJ0008 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4011a27b7e6707f9c9b4e3ed386306b00f2792cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317646"
---
# <a name="project-build-error-prj0008"></a>プロジェクト ビルド エラー PRJ0008
ファイル 'file' を削除できませんでした。  
  
 **ファイルが別のプロセスによって開かれていないと、書き込み保護されていないことを確認してください。**  
  
 Visual C がすべて正常中間出力ファイルをビルド、およびワイルドカードの仕様を満たすすべてのファイルを削除、再構築中に、または削除、**消去時に削除する拡張子**プロパティに、[全般構成の設定 プロパティ ページ](../../ide/general-property-page-project.md)です。  
  
 Visual C がファイルを削除できない場合は、このエラーが表示されます。 エラーを解決するには、ファイルとそのディレクトリを書き込み可能、ビルドを実行するユーザー用です。