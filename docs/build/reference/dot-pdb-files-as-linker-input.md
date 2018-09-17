---
title: .リンカー入力としての Pdb ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6b728903d2a270efc6b3eb736e45540651dae8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706187"
---
# <a name="pdb-files-as-linker-input"></a>リンカー入力としての .pdb ファイル

/Zi オプションを使用してコンパイルされた (.obj) ファイルがプログラム データベース (PDB) の名前を含むオブジェクトです。 リンカーは、オブジェクトの PDB ファイル名を指定しません。リンクは、必要な場合、PDB の検索に埋め込まれている名を使用します。 これをライブラリに含まれるデバッグ可能なオブジェクトにも当てはまりますデバッグ可能なライブラリの PDB は、リンカー、ライブラリと共に使用できるである必要があります。

リンクは、.exe ファイルまたは .dll ファイルのデバッグ情報を保持するためにも、PDB を使用します。 プログラムの PDB は、出力ファイルと、入力ファイルの両方をプログラムを再構築時に、リンクが pdb ファイルを更新ためです。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)