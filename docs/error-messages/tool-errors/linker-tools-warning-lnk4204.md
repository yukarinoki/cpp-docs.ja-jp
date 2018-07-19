---
title: リンカー ツールの警告 LNK4204 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4204
dev_langs:
- C++
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f000fa42357a299c943eda0cd5f8697aee138f4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300593"
---
# <a name="linker-tools-warning-lnk4204"></a>リンカー ツールの警告 LNK4204
'filename' は参照するモジュールのデバッグ情報がありません。オブジェクトをリンク デバッグ情報がありません。  
  
 .Pdb ファイルには、不適切な署名があります。 リンカーはデバッグ情報なしオブジェクトをリンクし続けます。 オブジェクト ファイルを使用して、再コンパイルすることができます、 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)オプション。  
  
 LNK4204 は、存在しなくなったファイルを参照して、ライブラリ内のオブジェクトの場合に発生することができます。 これは発生した可能性、ソリューションをリビルドするときに例を示します。オブジェクト ファイルは削除され、コンパイル エラーにより再構築されること可能性があります。 この場合、いずれかのコンパイル時に **/Z7**、または **/Fd**、1 つのファイルごとにライブラリ (は既定の .pdb ファイル名ではありません) を参照するオブジェクトを更新します。  詳細については、「[/Fd (プログラム データベース ファイル名)](../../build/reference/fd-program-database-file-name.md)」を参照してください。  ソース管理システムが更新されるたびに、ライブラリと .pdb ファイルを保存することを確認します。