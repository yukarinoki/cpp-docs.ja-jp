---
description: 詳細情報:/SUBSYSTEM (サブシステムの指定)
title: /SUBSYSTEM (サブシステムの指定)
ms.date: 11/04/2016
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
ms.openlocfilehash: 18a8ad549cc4aa1e143e43619d549c9eb7ae7324
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236244"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (サブシステムの指定)

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|
            POSIX|WINDOWS)
            [,major[.minor]]
```

## <a name="arguments"></a>引数

**BOOT_APPLICATION**<br/>
Windows のブート環境で実行するアプリケーションです。 ブートアプリケーションの詳細については、「 [BCD につい](/previous-versions/windows/desktop/bcd/about-bcd)て」を参照してください。

**CONSOLE**<br/>
Win32 文字モード アプリケーションに対して使用します。 オペレーティング システムには、コンソール アプリケーションのコンソールが用意されています。 ネイティブ コードに `main` または `wmain` が定義されている場合、マネージド コードに `int main(array<String ^> ^)` が定義されている場合、または `/clr:safe` を使用してアプリケーションを完全にビルドする場合、CONSOLE が既定の設定になります。

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
拡張可能なファームウェアインターフェイスサブシステム。 詳細については、EFI の仕様を参照してください。 例については、Intel の Web サイトを参照してください。 最小および既定のバージョンは 1.0 です。

**な**<br/>
Windows NT 用のカーネル モード ドライバーです。 このオプションは、通常、Windows システム コンポーネントのために予約されています。 [/DRIVER: WDM](driver-windows-nt-kernel-mode-driver.md)が指定されている場合、NATIVE が既定値です。

**POSIX**<br/>
Windows NT 上の POSIX サブシステムで実行するアプリケーションです。

**ウィンドウ**<br/>
アプリケーションにはコンソールは不要です。このシステムにはユーザーとの対話用のウィンドウが作成されるからです。 ネイティブ コードに `WinMain` または `wWinMain` が定義されている場合、あるいはマネージド コードに `WinMain(HISTANCE *, HINSTANCE *, char *, int)` または `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` が定義されている場合、WINDOWS が既定の設定になります。

*メジャー* と *マイナー*<br/>
Optionalサブシステムの最低限必要なバージョンを指定します。 引数には、0 ～ 65535 の範囲の 10 進数を指定します。 詳細については、「解説」を参照してください。 バージョン番号に上限はありません。

## <a name="remarks"></a>解説

**/SUBSYSTEM** オプションは、実行可能ファイルの環境を指定します。

サブシステムの選択によって、リンカーが選択するエントリ ポイント シンボル (またはエントリ ポイント関数) が決まります。

サブシステムの最小および既定の *メジャー* バージョン番号と *マイナー* バージョン番号は次のとおりです。

|Subsystem|最小値|Default|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1.0|1.0|
|CONSOLE|5.01 (x86) 5.02 (x64) 6.02 (ARM)|6.00 (x86、x64) 6.02 (ARM)|
|WINDOWS|5.01 (x86) 5.02 (x64) 6.02 (ARM)|6.00 (x86、x64) 6.02 (ARM)|
|NATIVE (DRIVER:WDM を使用する場合)|1.00 (x86) 1.10 (x64、ARM)|1.00 (x86) 1.10 (x64、ARM)|
|NATIVE (/DRIVER:WDM を使用しない場合)|4.00 (x86) 5.02 (x64) 6.02 (ARM)|4.00 (x86) 5.02 (x64) 6.02 (ARM)|
|POSIX|1.0|19.90|
|EFI_APPLICATION、EFI_BOOT_SERVICE_DRIVER、EFI_ROM、EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [リンカー] フォルダーを選択します。

1. [ **システム** ] プロパティページを選択します。

1. `SubSystem` プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
