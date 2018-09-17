---
title: .リンカー入力として Obj ファイル |Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: decd015a184b66fa5867435177c07fdf23ad53ae
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704380"
---
# <a name="obj-files-as-linker-input"></a>リンカー入力としての .obj ファイル

リンカー ツール (リンク。EXE) では、一般的なオブジェクト ファイル形式 (COFF) での .obj ファイルを受け入れます。

## <a name="remarks"></a>Remarks

Microsoft では、一般的なオブジェクト ファイル形式の完全な説明を提供します。 詳細については、次を参照してください。 [PE 形式](/windows/desktop/Debug/pe-format)します。

## <a name="unicode-support"></a>Unicode のサポート

Visual Studio 2005 以降では、Microsoft Visual C コンパイラは、ISO/IEC C および C++ 標準で定義されている識別子の Unicode 文字をサポートします。 以前のバージョンのコンパイラでは、識別子で ASCII 文字のみがサポートされています。 関数、クラス、および静的変数の名前で Unicode をサポートするために、コンパイラとリンカーは、COFF シンボル .obj ファイル内の Unicode utf-8 エンコードを使用して。 Utf-8 エンコーディングは、Visual Studio の以前のバージョンで使用される ASCII エンコーディングと互換性のある上方は。

コンパイラとリンカーの詳細については、次を参照してください。[コンパイラおよびリンカーで Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)します。 Unicode 規格の詳細については、次を参照してください。、 [Unicode](http://www.unicode.org/)組織。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
[Unicode のサポート](../../text/support-for-unicode.md)<br/>
[コンパイラおよびリンカーでの Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)<br/>
[Unicode 標準](http://www.unicode.org/)<br/>
[PE 形式](/windows/desktop/Debug/pe-format)
