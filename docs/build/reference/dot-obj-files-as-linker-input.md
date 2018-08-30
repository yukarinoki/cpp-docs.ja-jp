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
ms.openlocfilehash: ffbc1d7fc7f74121c37c9e80a538ec60f2265701
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219563"
---
# <a name="obj-files-as-linker-input"></a>リンカー入力としての .obj ファイル

リンカー ツール (リンク。EXE) では、一般的なオブジェクト ファイル形式 (COFF) での .obj ファイルを受け入れます。

## <a name="remarks"></a>Remarks

Microsoft では、一般的なオブジェクト ファイル形式の完全な説明を提供します。 詳細については、次を参照してください。 [PE 形式](/windows/desktop/Debug/pe-format)します。

## <a name="unicode-support"></a>Unicode のサポート

Visual Studio 2005 以降では、Microsoft Visual C コンパイラは、ISO/IEC C および C++ 標準で定義されている識別子の Unicode 文字をサポートします。 以前のバージョンのコンパイラでは、識別子で ASCII 文字のみがサポートされています。 関数、クラス、および静的変数の名前で Unicode をサポートするために、コンパイラとリンカーは、COFF シンボル .obj ファイル内の Unicode utf-8 エンコードを使用して。 Utf-8 エンコーディングは、Visual Studio の以前のバージョンで使用される ASCII エンコーディングと互換性のある上方は。

コンパイラとリンカーの詳細については、次を参照してください。[コンパイラおよびリンカーで Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)します。 Unicode 規格の詳細については、次を参照してください。、 [Unicode](http://go.microsoft.com/fwlink/p/?linkid=37123)組織。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)  
[リンカー オプション](../../build/reference/linker-options.md)  
[Unicode のサポート](../../text/support-for-unicode.md)  
[コンパイラおよびリンカーでの Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Unicode 標準](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[PE 形式](/windows/desktop/Debug/pe-format)  
