---
description: 詳細については、「」を参照してください。リンカー入力としての Pdb ファイル
title: リンカー入力としての .pdb ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 713d42e7e95b5d1e7e3b1f9be21203b75569cdbe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201158"
---
# <a name="pdb-files-as-linker-input"></a>リンカー入力としての .pdb ファイル

/Zi オプションを使用してコンパイルされたオブジェクト (.obj) ファイルには、プログラムデータベース (PDB) の名前が含まれています。 リンカーに対してオブジェクトの PDB ファイル名を指定することはできません。リンクでは、必要に応じて、埋め込み名を使用して PDB を検索します。 これは、ライブラリに含まれるデバッグ可能なオブジェクトにも適用されます。デバッグ可能なライブラリの PDB は、ライブラリと共にリンカーで使用できる必要があります。

また、PDB を使用して、.exe ファイルまたは .dll ファイルのデバッグ情報を保持します。 プログラムの PDB は、プログラムのリビルド時にリンクによって PDB が更新されるため、出力ファイルと入力ファイルの両方になります。

## <a name="see-also"></a>関連項目

[リンク入力ファイル](link-input-files.md)<br/>
[MSVC リンカー オプション](linker-options.md)
