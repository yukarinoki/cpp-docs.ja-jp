---
title: リンカー ツールの警告 LNK4204 |Microsoft Docs
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
ms.openlocfilehash: ee6164f20bbf91a8cb0b88d8a1333107f239d3f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136238"
---
# <a name="linker-tools-warning-lnk4204"></a>リンカー ツールの警告 LNK4204

'filename' が参照するモジュールのデバッグ情報がありません。デバッグ情報オブジェクトをリンク

.Pdb ファイルには、エラーのある署名があります。 リンカーでは、引き続きデバッグ情報なしオブジェクトをリンクします。 オブジェクト ファイルを使用して、再コンパイルすることも、 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)オプション。

LNK4204 は、存在しなくなったファイルを参照してください、ライブラリ内のオブジェクトのいくつかの場合に発生することができます。 これは、現象は、ソリューションを再構築するときなどです。オブジェクト ファイルは削除され、コンパイル エラーのため再構築しない可能性があります。 使用してこの例では、いずれかのコンパイル **/Z7**、または **/Fd**、1 つのファイルごとにライブラリを (既定の .pdb ファイル名ではありません) を参照するオブジェクトを更新します。  詳細については、「[/Fd (プログラム データベース ファイル名)](../../build/reference/fd-program-database-file-name.md)」を参照してください。  ソース管理システムで更新されるたびに、ライブラリと .pdb ファイルが保存されていることを確認します。