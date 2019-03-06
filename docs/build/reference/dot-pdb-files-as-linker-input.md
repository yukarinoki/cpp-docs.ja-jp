---
title: リンカー入力としての .pdb ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: a29f01e5e5b30be4f7a983652d476a4512d2bec0
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426426"
---
# <a name="pdb-files-as-linker-input"></a>リンカー入力としての .pdb ファイル

/Zi オプションを使用してコンパイルされた (.obj) ファイルがプログラム データベース (PDB) の名前を含むオブジェクトです。 リンカーは、オブジェクトの PDB ファイル名を指定しません。リンクは、必要な場合、PDB の検索に埋め込まれている名を使用します。 これをライブラリに含まれるデバッグ可能なオブジェクトにも当てはまりますデバッグ可能なライブラリの PDB は、リンカー、ライブラリと共に使用できるである必要があります。

リンクは、.exe ファイルまたは .dll ファイルのデバッグ情報を保持するためにも、PDB を使用します。 プログラムの PDB は、出力ファイルと、入力ファイルの両方をプログラムを再構築時に、リンクが pdb ファイルを更新ためです。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
