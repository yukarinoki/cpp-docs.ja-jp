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
ms.openlocfilehash: 0b3fa8bcfd973949e73fdf701db2adb6c58be687
ms.sourcegitcommit: 2f9ff2041d70c406df76c5053151192aad3937ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "82587385"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (ターミナル サーバーに対応したアプリケーションの作成)

```
/TSAWARE[:NO]
```

## <a name="remarks"></a>Remarks

/TSAWARE オプションは、プログラムイメージの省略可能なヘッダーの IMAGE_OPTIONAL_HEADER DllCharacteristics フィールドにフラグを設定します。 このフラグが設定されると、ターミナル サーバーはアプリケーションに特定の変更を加えなくなります。

ターミナルサーバー対応 (レガシアプリケーションとも呼ばれます) でないアプリケーションは、マルチユーザー環境で正常に動作するように、レガシアプリケーションに対して特定の変更を行います。 たとえば、ターミナルサーバーは、windows の Windows ディレクトリを取得するのではなく、各ユーザーが Windows フォルダーを取得するように、仮想 Windows フォルダーを作成します。 これにより、ユーザーは独自の INI ファイルにアクセスできるようになります。 さらに、ターミナルサーバーは、レガシアプリケーションのレジストリに対していくつかの調整を行います。 これらの変更により、ターミナルサーバーでのレガシアプリケーションの読み込みが遅くなります。

アプリケーションがターミナルサーバーに対応している場合は、セットアップ中に INI ファイルに依存したり、 **HKEY_CURRENT_USER**レジストリに書き込むことはできません。

/TSAWARE を使用していて、アプリケーションが INI ファイルを引き続き使用している場合、ファイルはシステムのすべてのユーザーによって共有されます。 これが許容される場合でも、アプリケーションを/TSAWARE にリンクすることはできます。それ以外の場合は、/TSAWARE: NO を使用する必要があります。

/TSAWARE オプションは、Windows およびコンソールアプリケーションでは既定で有効になっています。 詳細については、「 [/SUBSYSTEM](subsystem-specify-subsystem.md) and [/VERSION](version-version-information.md) 」を参照してください。

/TSAWARE は、ドライバーまたは Dll では無効です。

アプリケーションが/TSAWARE とリンクされている場合、その効果についての情報が[表示され](headers.md)ます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [**システム**] プロパティページをクリックします。

1. **ターミナルサーバー**のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A> 」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[ユーザー固有の情報の格納](/windows/win32/TermServ/storing-user-specific-information)<br/>
[ターミナルサービス環境でのレガシアプリケーション](https://msdn.microsoft.com/library/aa382957.aspx)
