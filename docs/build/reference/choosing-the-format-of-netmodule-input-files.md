---
title: .netmodule 入力ファイルの形式の選択
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: 92f7aafa102a8591192f4394aee62afe86bb3549
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444318"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule 入力ファイルの形式の選択

MSIL の .obj ファイル (でコンパイルされた[/clr](../../build/reference/clr-common-language-runtime-compilation.md)) .netmodule ファイルとしても使用できます。  .obj ファイルには、メタデータとネイティブのシンボルが含まれます。  .netmodule には、メタデータにはのみが含まれます。

できます/addmodule コンパイラ オプションを使用して、MSIL の .obj ファイルをその他の Visual Studio コンパイラに渡す (が .obj ファイルは、生成されたアセンブリの一部になるし、アセンブリに付属する必要がありますに注意してください)。  たとえば、Visual c# および Visual Basic には、/addmodule コンパイラ オプションがあります。

> [!NOTE]
>  ほとんどの場合は、.net モジュールを作成したコンパイルの .obj ファイルをリンカーに渡す必要があります。  .Dll または .netmodule の MSIL モジュールのファイルをリンカーに渡すと、LNK1107 可能性があります。

.obj ファイルを使用して参照するには関連付けられている .h ファイルと一緒に # ソースに include、.netmodule ファイルで、C++ アプリケーションでマネージ型のみを使用できますが、モジュール内のネイティブ型を使用する C++ アプリケーションを許可します。  .Obj ファイルをしようとした場合は、# を using ネイティブ型に関する情報は使用できません。# 代わりに include .obj ファイルの .h ファイル。

その他の Visual Studio コンパイラは、モジュールからのマネージ型のみを使用できます。

次を使用すると、Visual C リンカーへのモジュールの入力としての .netmodule または .obj ファイルを使用するのに必要があるかどうかを決定します。

- Visual C 以外の Visual Studio コンパイラを構築している場合、.netmodule を生成およびリンカーへの入力として、.netmodule を使用します。

- モジュールとモジュールがライブラリ以外のものをビルドに使用されるかどうかに生成するために、Visual C コンパイラを使用する場合は、モジュール、リンカー入力として、コンパイラによって生成された .obj ファイルを使用してください。入力としての .netmodule ファイルを使わないでください。

- ネイティブ、マネージ ライブラリをビルドするモジュールを使用する場合は、リンカーへのモジュールの入力としての .obj ファイルを使用し、.lib ライブラリ ファイルを生成します。

- モジュールを使用して、マネージ ライブラリをビルドして、リンカーへのすべてのモジュール入力する場合は検証可能 (/clr:safe により生成) は、リンカーへのモジュールの入力としての .obj ファイルを使用し、(アセンブリ) .dll または .netmodule (モジュール) ライブラリのファイルを生成します。

- モジュールを使用して、マネージ ライブラリをビルドして、リンカーに 1 つまたは複数のモジュールの入力は単なる/clr で生成する場合は、リンカーへのモジュールの入力としての .obj ファイルを使用し、.dll (アセンブリ) を生成します。  ライブラリ コンポーネント モジュール (はもに送付する各モジュールの .h ファイルの .obj ファイルのライブラリでは、ライブラリからのマネージ型とする場合も、ライブラリ内のネイティブ型を使用する C++ アプリケーションを公開する場合は、、を参照できるように #include ソース コードから)。

## <a name="see-also"></a>関連項目

[.netmodule ファイル (リンカー入力)](../../build/reference/netmodule-files-as-linker-input.md)