---
title: プロジェクトのビルドの警告 PRJ0041 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e845967b0a7116d6edade98b571de5bc1bcd9a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-warning-prj0041"></a>プロジェクト ビルドの警告 PRJ0041
見つかりません 'への依存関係' ファイル 'file' の依存関係。 プロジェクトがビルドできますは、このファイルが見つかるまで、最新バージョンを続けることがあります。  
  
 ファイル (リソース ファイルや.idl/.odl ファイル、たとえば、包含 include ステートメントが、プロジェクト システムを解決できませんでした。  
  
 プロジェクト システムがプリプロセッサ ステートメント (#if など) を処理できないため、問題が発生したステートメント実際にできないビルドの一部。  
  
 この警告を解決するには、.rc ファイル内のすべての不要なコードを削除するか、適切な名前のプレース ホルダー ファイルを追加します。