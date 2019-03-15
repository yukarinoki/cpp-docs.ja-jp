---
title: /TSAWARE (ターミナル サーバーに対応したアプリケーションの作成)
ms.date: 11/04/2016
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
ms.openlocfilehash: f6ed6184f8ae4b3a0f9db3c1f962a2918a185138
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816946"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (ターミナル サーバーに対応したアプリケーションの作成)

```
/TSAWARE[:NO]
```

## <a name="remarks"></a>Remarks

/TSAWARE オプションは、プログラム イメージの省略可能なヘッダーのある IMAGE_OPTIONAL_HEADER DllCharacteristics フィールドにフラグを設定します。 このフラグが設定されると、ターミナル サーバーはアプリケーションに特定の変更を加えなくなります。

アプリケーションは、ターミナル サーバーに注意してください (レガシ アプリケーションとも呼ばれます) ではない、ターミナル サーバーはマルチ ユーザー環境で正しく動作するように、レガシ アプリケーションに対して特定の変更を使用します。 たとえば、ターミナル サーバーであっても、各ユーザーがシステムの Windows ディレクトリを取得する代わりに、Windows フォルダーを取得するよう、仮想の Windows フォルダーが作成されます。 これにより、ユーザーは自分の INI ファイルにアクセスできるようにします。 さらに、ターミナル サーバーは、レガシ アプリケーション用にレジストリを調整します。 これらの変更には、ターミナル サーバーでレガシ アプリケーションの読み込みが低速です。

アプリケーションがターミナル サーバーに対応した場合、その必要があります INI ファイルに依存してもへの書き込み、 **HKEY_CURRENT_USER**セットアップ中にレジストリ。

/TSAWARE を使用すると、アプリケーションがまだ INI ファイルを使用して、ファイルは、システムのすべてのユーザーによって共有されます。 許容される場合は、まだ/TSAWARE; を使用してアプリケーションをリンクできます。それ以外の場合は、/TSAWARE:NO を使用する必要があります。

このオプションは、Windows アプリケーションとコンソール アプリケーションの既定で有効です。 参照してください[/SUBSYSTEM](subsystem-specify-subsystem.md)と[/VERSION](version-version-information.md)について。

/TSAWARE は、ドライバー、Vxd の Dll に対して無効です。

アプリケーションの/TSAWARE、DUMPBIN は関連付け[/HEADERS](headers.md)それに対応する情報が表示されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**システム**プロパティ ページ。

1. 変更、**ターミナル サーバー**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[ユーザー固有の情報を格納します。](/windows/desktop/TermServ/storing-user-specific-information)<br/>
[ターミナル サービス環境でレガシ アプリケーション](https://msdn.microsoft.com/library/aa382957.aspx)
