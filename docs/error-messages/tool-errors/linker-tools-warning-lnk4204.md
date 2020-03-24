---
title: リンカー ツールの警告 LNK4204
ms.date: 11/04/2016
f1_keywords:
- LNK4204
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
ms.openlocfilehash: 98c53c9b998e9bd544c1cc72bd2b0c3fd2b0a418
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193863"
---
# <a name="linker-tools-warning-lnk4204"></a>リンカー ツールの警告 LNK4204

' filename ' には参照するモジュールのデバッグ情報がありません。デバッグ情報がない場合と同様にオブジェクトをリンクしています

.Pdb ファイルの署名が間違っています。 リンカーは、デバッグ情報なしでオブジェクトをリンクし続けます。 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)オプションを使用して、オブジェクトファイルを再コンパイルすることもできます。

LNK4204 は、ライブラリ内の一部のオブジェクトが、存在しなくなったファイルを参照している場合に発生する可能性があります。 これは、たとえば、ソリューションを再構築するときに発生する可能性があります。オブジェクトファイルは、コンパイルエラーのために削除され、再構築されない可能性があります。 この場合は、 **/Z7**( **/fd**) を使用してコンパイルし、ライブラリごとに1つのファイルを参照するようにオブジェクトを更新します (既定の .pdb ファイル名ではありません)。  詳細については、「[/Fd (プログラム データベース ファイル名)](../../build/reference/fd-program-database-file-name.md)」を参照してください。  ソース管理システムで更新されるたびに、.pdb がライブラリと共に保存されていることを確認します。
