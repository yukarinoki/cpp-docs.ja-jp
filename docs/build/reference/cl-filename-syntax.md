---
description: '詳細情報: CL ファイル名の構文'
title: CL ファイル名の構文
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: c7a657b54f69e2cdc0a126c55bb4102589a84290
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182442"
---
# <a name="cl-filename-syntax"></a>CL ファイル名の構文

CL は、名前が FAT、HPFS、NTFS のいずれかの名前付け規則に従っているファイルを受け入れます。 いずれのファイル名にも、完全なパスまたは相対パスを含めることができます。 完全なパスには、ドライブ名と 1 つ以上のディレクトリ名が含まれます。 CL は、円記号 ( \\ ) またはスラッシュ (/) で区切られたファイル名を受け入れます。 スペースが含まれるファイル名は、二重引用符文字で囲む必要があります。 相対パスではドライブ名を省略し、CL ではドライブが現在のドライブであると想定します。 パスを指定しない場合は、CL は、ファイルが現在のディレクトリにあると想定します。

ファイル名拡張子によって、ファイルの処理方法が決定されます。 拡張子が .c、.cxx、.cpp である、C および C++ ファイルはコンパイルされます。 .obj ファイル、ライブラリ (.lib)、モジュール定義 (.def) ファイルなどのその他のファイルは、処理されずにリンカーに渡されます。

## <a name="see-also"></a>関連項目

[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
