---
title: コンパイラとリンカーのオプション (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e43418555722090c325c85bd4e77204640791b32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-and-linker-options-ccx"></a>コンパイラとリンカーのオプション (C++/CX)
環境変数、C + + CX コンパイラ オプションとリンカーのオプションは、Windows ランタイム アプリの構築をサポートします。  
  
## <a name="library-path"></a>ライブラリのパス  
 %LIBPATH% 環境変数は、.winmd ファイルを検索するための既定パスを指定します。  
  
## <a name="compiler-options"></a>コンパイラ オプション  
  
|オプション|説明|  
|------------|-----------------|  
|[/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> /ZW:nostdlib|Windows ランタイム言語拡張機能を有効にします。<br /><br /> `nostdlib` パラメーターは、コンパイラが、アセンブリと .winmd ファイルの検索に標準の定義済み検索パスを使用しないようにします。<br /><br /> **/ZW** コンパイラ オプションは、暗黙的に次のコンパイラ オプションを指定します。<br /><br /> -   **/FI** vccorlib.h で、コンパイラで必要となるさまざまな種類を定義する vccorlib.h ヘッダー ファイルのインクルードを強制します。<br />-   [/FU](../build/reference/fu-name-forced-hash-using-file.md) Windows.winmd で、オペレーティング システムによって提供され、Windows ランタイムでさまざまな種類を定義する Windows.winmd メタデータ ファイルのインクルードを強制します。<br />-   **/FU** Platform.winmd - コンパイラが提供し、名前空間のプラットフォーム ファミリのほとんどの型を定義する Platform.winmd メタデータ ファイルのインクルードを強制します。|  
|[/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|*dir* パラメーターに指定されたディレクトリを、コンパイラがアセンブリと .winmd ファイルを検索するために使用する検索パスに追加します。|  
|**/FU**  *ファイル*|指定されたモジュールまたは .winmd ファイルのインクルードを強制します。 つまり、ソース コード内に `#using`*file* を指定する必要はありません。 コンパイラは、独自の Windows メタデータ ファイル Platform.winmd のインクルードを自動的に強制します。|  
|/D"WINAPI_FAMILY = 2"|Windows ランタイムと互換性のある Win32 SDK のサブセットの使用を有効にする定義を作成します。|  
  
## <a name="linker-options"></a>リンカー オプション  
  
|オプション|説明|  
|------------|-----------------|  
|/APPCONTAINER[:NO]|実行可能ファイルを、AppContainer (のみ) で実行可能としてマークを付けます。|  
|/WINMD[:{NO&#124;ONLY}]|.winmd ファイルと関連するバイナリ ファイルを生成します。 このオプションは、生成する .winmd のリンカーに渡す必要があります。<br /><br /> **NO**—.winmd ファイルは生成しませんが、バイナリ ファイルを生成します。<br /><br /> **ONLY**—..winmd ファイルを生成しますが、バイナリ ファイルは生成しません。|  
|/WINMDFILE:*filename*|生成する .winmd ファイルの名前。既定の .winmd ファイル名の代わりに使用されます。 コマンド ラインで複数のファイル名を指定すると、最後の名前が使用されます。|  
|/WINMDDELAYSIGN[:NO]|部分的に .winmd ファイルに署名し、公開キーをバイナリに配置します。<br /><br /> **NO**—(既定) .winmd ファイルに署名しません。<br /><br /> /WINMDKEYFILE または /WINMDKEYCONTAINER も指定しないかぎり、/WINMDDELAYSIGN の影響はありません。|  
|/WINMDKEYCONTAINER:*name*|アセンブリに署名するためのキー コンテナーを指定します。 *name* パラメーターは、メタデータ ファイルの署名に使用するキー コンテナーに対応します。|  
|/WINMDKEYFILE:*filename*|アセンブリに署名するためのキーまたはキー ペアを指定します。 *filename* パラメーターは、メタデータ ファイルの署名に使用するキーに対応します。|  
  
### <a name="remarks"></a>コメント  
 **/ZW**が使用されると、コンパイラは DLL バージョンの C ランタイム (CRT) に自動的にリンクします。 スタティック ライブラリ バージョンへのリンクが許可されていません。 とユニバーサル Windows プラットフォーム アプリで許可されていない CRT 関数を使用するには、コンパイル時エラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [アプリのビルドとライブラリ](../cppcx/building-apps-and-libraries-c-cx.md)