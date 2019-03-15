---
title: リンカー入力としての .pdb ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 365f2955f5bc9e8082221a070af454c820c665f1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822523"
---
# <a name="pdb-files-as-linker-input"></a>リンカー入力としての .pdb ファイル

/Zi オプションを使用してコンパイルされた (.obj) ファイルがプログラム データベース (PDB) の名前を含むオブジェクトです。 リンカーは、オブジェクトの PDB ファイル名を指定しません。リンクは、必要な場合、PDB の検索に埋め込まれている名を使用します。 これをライブラリに含まれるデバッグ可能なオブジェクトにも当てはまりますデバッグ可能なライブラリの PDB は、リンカー、ライブラリと共に使用できるである必要があります。

リンクは、.exe ファイルまたは .dll ファイルのデバッグ情報を保持するためにも、PDB を使用します。 プログラムの PDB は、出力ファイルと、入力ファイルの両方をプログラムを再構築時に、リンクが pdb ファイルを更新ためです。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](link-input-files.md)<br/>
[MSVC リンカー オプション](linker-options.md)
