---
title: .リンカー入力として Pdb ファイル |Microsoft ドキュメント
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
ms.openlocfilehash: f6707be955b5c4a332d1162f53b1cb854391a2ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370177"
---
# <a name="pdb-files-as-linker-input"></a>リンカー入力としての .pdb ファイル
/Zi オプションを使用してコンパイルされる (.obj) ファイルは、プログラム データベース (PDB) の名前を含むオブジェクトです。 リンカー; に、オブジェクトの PDB ファイル名を指定しません。リンクでは、埋め込み名を使用して、必要な場合は、pdb ファイルを探します。 これはライブラリに含まれるデバッグ可能なオブジェクトにも適用されます。デバッグ可能なライブラリの PDB は、ライブラリと共にリンカーを使用できなければなりません。  
  
 また、リンクは、.exe ファイルまたは .dll ファイルのデバッグ情報を保持するために PDB を使用します。 プログラムの PDB は、出力ファイルと、入力ファイルの両方は、プログラムを再構築時に、リンクが pdb ファイルを更新するためです。  
  
## <a name="see-also"></a>関連項目  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)