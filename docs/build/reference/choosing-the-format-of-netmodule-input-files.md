---
title: .netmodule 入力ファイルの形式の選択
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: b4d4b80e4b9195d184b9d97cea67bbaaa3d7d843
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320572"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule 入力ファイルの形式の選択

MSIL .obj ファイル ( [/clr](clr-common-language-runtime-compilation.md)でコンパイル ) は、.netmodule ファイルとしても使用できます。  .obj ファイルには、メタデータとネイティブ シンボルが含まれています。  .net モジュールにはメタデータのみが含まれています。

/addmodule コンパイラ オプションを使用して、他の Visual Studio コンパイラに MSIL .obj ファイルを渡すことができます (ただし、.obj ファイルは結果のアセンブリの一部となり、アセンブリに付属する必要があることに注意してください)。  たとえば、Visual C# と Visual Basic には、/addmodule コンパイラ オプションがあります。

> [!NOTE]
> ほとんどの場合、.net モジュールを作成したコンパイルから .obj ファイルをリンカーに渡す必要があります。  .dll または .netmodule MSIL モジュール ファイルをリンカーに渡すと、LNK1107 が発生する可能性があります。

ソース内の#includeを介して参照する .obj ファイルと関連付けられた .h ファイルは、C++ アプリケーションがモジュール内のネイティブ型を使用できるようにしますが、.netmodule ファイルでは、C++ アプリケーションで使用できるのはマネージ型だけです。  obj ファイルを#usingに渡そうとすると、ネイティブ型に関する情報は利用できません。代わりに、.obj ファイルの .h ファイルを#includeします。

他の Visual Studio コンパイラは、モジュールからのマネージ型のみを使用できます。

MSVC リンカーへのモジュール入力として .netmodule または .obj ファイルを使用する必要があるかどうかを判断するには、次の手順を実行します。

- Visual C++ 以外の Visual Studio コンパイラを使用してビルドする場合は、.netmodule を生成し、リンカーへの入力として .netmodule を使用します。

- MSVC コンパイラを使用してモジュールを生成し、モジュールを使用してライブラリ以外のビルドを行う場合は、リンカーへのモジュール入力としてコンパイラによって生成された .obj ファイルを使用します。.netmodule ファイルを入力として使用しないでください。

- モジュールを使用してネイティブ ライブラリ (マネージ ライブラリではない) をビルドする場合は、リンカーへのモジュール入力として .obj ファイルを使用し、.lib ライブラリ ファイルを生成します。

- モジュールを使用してマネージ ライブラリをビルドし、リンカーへのすべてのモジュール入力が検証可能 (/clr:safe で生成される) 場合は、リンカーへのモジュール入力として .obj ファイルを使用し、.dll (アセンブリ) または .netmodule (モジュール) ライブラリ ファイルを生成します。

- モジュールを使用してマネージ ライブラリをビルドし、リンカーに入力された 1 つ以上のモジュールが /clr だけで生成される場合は、リンカーへのモジュール入力として .obj ファイルを使用し、.dll (アセンブリ) を生成します。  ライブラリからマネージ型を公開する場合、C++ アプリケーションもライブラリ内のネイティブ型を使用する場合、ライブラリはライブラリ コンポーネント モジュールの .obj ファイルで構成されます (各モジュールの .h ファイルも出荷して、ソース コードから#includeで参照できるようにします)。

## <a name="see-also"></a>関連項目

[.netmodule ファイル (リンカー入力)](netmodule-files-as-linker-input.md)
