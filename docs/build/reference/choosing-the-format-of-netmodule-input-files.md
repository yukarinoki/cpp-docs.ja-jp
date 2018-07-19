---
title: .Netmodule の形式を選択する入力ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62575d3e816bdc10587e7a4c9cebcea735329ec1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372722"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule 入力ファイルの形式の選択
MSIL .obj ファイル (でコンパイルされた[/clr](../../build/reference/clr-common-language-runtime-compilation.md)) .netmodule ファイルとしても使用できます。  .obj ファイルには、メタデータおよびネイティブ シンボルが含まれます。  .netmodule には、メタデータにはのみが含まれています。  
  
 できますが、/addmodule コンパイラ オプションを使用して、他の Visual Studio コンパイラに MSIL .obj ファイルを渡す (は、.obj ファイルは、生成されたアセンブリの一部になるし、アセンブリと共に出荷する必要がありますに注意してください)。  たとえば、Visual c# および Visual Basic/addmodule コンパイラ オプションがあります。  
  
> [!NOTE]
>  ほとんどの場合は、.net モジュールを作成するコンパイルから .obj ファイルをリンカーに渡す必要があります。  .Dll ファイルまたは .netmodule の MSIL モジュールのファイルをリンカーに渡すと、LNK1107 可能性があります。  
  
 .obj ファイルから参照を関連付けられている .h ファイルと一緒に # 元に、include、C++ アプリケーションで使用できるマネージ型のみ .netmodule ファイルに対し、モジュールでは、ネイティブ型を使用する C++ アプリケーションを許可します。  .Obj ファイルに渡すしようとすると #using、ネイティブ型に関する情報は使用できません。#include .obj ファイルの .h ファイル代わりにします。  
  
 他の Visual Studio コンパイラは、モジュールからのマネージ型のみを使用できます。  
  
 .Netmodule または .obj ファイルを Visual C リンカーのモジュールの入力として使用するのに必要があるかどうかを決定するのにには、次を使用します。  
  
-   Visual C 以外の Visual Studio コンパイラで構築する、.netmodule を生成しをリンカー入力として、.netmodule を使用します。  
  
-   モジュールを生成し、モジュールはライブラリ以外のものをビルドに使用するかどうか、Visual C コンパイラを使用している場合は、リンカーへのモジュールの入力として、コンパイラによって生成された .obj ファイルを使用してください。入力としては、.netmodule ファイルを使用しないでください。  
  
-   場合は、モジュールを使用して、マネージ ネイティブ ライブラリをビルド、.obj ファイルをリンカーにモジュールの入力として使用し、.lib ライブラリ ファイルを生成します。  
  
-   モジュールを使用して、マネージ ライブラリをビルドし、リンカーへのすべてのモジュール入力は検証可能である (/clr:safe で生成される) 場合は、.obj ファイルをリンカーにモジュールの入力として使用し、.dll ファイル (アセンブリ) または .netmodule (モジュール) のライブラリ ファイルを生成します。  
  
-   マネージ ライブラリをビルドに使用される、モジュール、リンカーに 1 つまたは複数のモジュールの入力は単なる/clr で生成する場合、リンカーにモジュールの入力としての .obj ファイルを使用し、.dll (アセンブリ) を生成します。  ライブラリ コンポーネント モジュール (、また出荷する各モジュールの .h ファイルの .obj ファイルのライブラリでは、ライブラリからのマネージ型とする場合も、ライブラリ内のネイティブ型を使用する C++ アプリケーションを公開する場合は、、を参照できるように # ソース コードから include)。  
  
## <a name="see-also"></a>関連項目  
 [.netmodule ファイル (リンカー入力)](../../build/reference/netmodule-files-as-linker-input.md)