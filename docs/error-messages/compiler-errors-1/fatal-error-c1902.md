---
title: 致命的なエラー C1902 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b23507b6531f9ee4e5ce5efd5b60a1977206635c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228200"
---
# <a name="fatal-error-c1902"></a>致命的なエラー C1902
プログラム データベース マネージャーが一致しません。インストールを確認してください。  
  
プログラム データベース ファイル (.pdb) が新しいバージョンの mspdb を使用して作成された*XXX*.dll、コンパイラは、システムで見つかったものです。 このエラーは、通常 mspdbsrv.exe または mspdbcore.dll が見つからないか、mspdb とは異なるバージョンがあることに示す*XXX*.dll です。 (、 *XXX* 、mspdb 内のプレース ホルダー*XXX*製品リリースされるたびに .dll ファイル名の変更。 例については、Visual Studio 2015 では、ファイル名は mspdb140.dll です。)  
  
Mspdbsrv.exe、mspdbcore.dll、および mspdb の一致するバージョンを確認してください*XXX*.dll は、システムにインストールします。 バージョンが一致しませんが、ターゲット プラットフォームのコンパイラおよびリンクのツールが含まれているディレクトリにコピーされていないことを確認します。 たとえば、可能性がありますがファイルをコピーした、設定を指定せず、コマンド プロンプトから、コンパイラやリンク ツールを起動できるように、**パス**環境変数に応じて。