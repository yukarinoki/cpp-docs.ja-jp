---
description: 詳細については、「パス名の指定」を参照してください。
title: パス名の指定
ms.date: 11/04/2016
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
ms.openlocfilehash: a8c55822bcb19864955ffa37ef2dd4cb18765ae5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224531"
---
# <a name="specifying-the-pathname"></a>パス名の指定

各出力ファイルオプションは、出力ファイルの場所と名前を指定できる *pathname* 引数を受け取ります。 引数には、ドライブ名、ディレクトリ、およびファイル名を含めることができます。 オプションと引数の間にスペースを使用することはできません。

*パス* 名に拡張子のないファイル名が含まれている場合、コンパイラは既定の拡張子を出力します。 *Pathname* にディレクトリが含まれていてもファイル名がない場合、コンパイラは指定されたディレクトリに既定の名前でファイルを作成します。 既定の名前は、ソースファイルの基本名と、出力ファイルの種類に基づく既定の拡張機能に基づいています。 *パス名* を完全に省略した場合、コンパイラは既定のディレクトリに既定の名前でファイルを作成します。

また、 *pathname* 引数には、ファイル名ではなくデバイス名 (AUX、CON、PRN、または NUL) を指定できます。 デバイス名の一部として、オプションとデバイス名またはコロンの間にスペースを使用しないでください。

|デバイス名|表す内容|
|-----------------|----------------|
|AUX|補助デバイス|
|CON|コンソール|
|PRN|プリンター|
|NUL|Null デバイス (ファイルが作成されていません)|

## <a name="example"></a>例

次のコマンドラインは、マップをプリンターに送信します。

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
