---
title: BSCMAKE エラー BK1513 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93664a1224b85ec808805da0172aec408e875bc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295741"
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE エラー BK1513
インクリメンタルでないビルドにはすべての .SBR ファイルが必要です。  
  
 1 つ以上の .sbr ファイルが切り捨てられたため、BSCMAKE では、新しいブラウザー情報 (.bsc) ファイルをビルドできません。 切り捨てられた .sbr ファイルの名前を検索するには、読み取り、 [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md)このエラーを警告します。  
  
 BSCMAKE では .bsc ファイルを切り捨てられた .sbr ファイルで更新できますが、新しいものをビルドすることはできません。 BSCMAKE では、次の理由で新しい .bsc ファイルをビルドする可能性があります。  
  
-   .bsc ファイルが欠落しています。  
  
-   .bsc ファイルに指定されたファイル名が間違っています。  
  
-   .bsc ファイルが破損しています。  
  
 この問題を解決するには、切り捨てられた .sbr ファイルを削除して再ビルドするか、または、ソリューションをクリーンして再ビルドします。 (IDE では、次のように選択します**ビルド**、**ソリューションのクリーン**、を選択し**ビルド**、**ソリューションのリビルド**。)。