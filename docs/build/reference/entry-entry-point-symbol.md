---
description: 詳細情報:/ENTRY (エントリポイントシンボル)
title: /ENTRY (エントリ ポイント シンボル)
ms.date: 11/04/2016
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
ms.openlocfilehash: e4966ef44922a3a90d5abb5a7ac23460d4155f92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201015"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (エントリ ポイント シンボル)

```
/ENTRY:function
```

## <a name="arguments"></a>引数

*function*<br/>
.Exe ファイルまたは DLL のユーザー定義の開始アドレスを指定する関数。

## <a name="remarks"></a>解説

/ENTRY オプションは、.exe ファイルまたは DLL の開始アドレスとしてエントリポイント関数を指定します。

呼び出し規約を使用するには、関数を定義する必要があり **`__stdcall`** ます。 パラメーターと戻り値は、プログラムがコンソールアプリケーション、windows アプリケーション、または DLL のいずれであるかによって異なります。 C ランタイムライブラリが正しく初期化されるようにリンカーにエントリポイントを設定し、静的オブジェクトの C++ コンストラクターを実行することをお勧めします。

既定では、開始アドレスは C ランタイムライブラリの関数名です。 リンカーは、次の表に示すように、プログラムの属性に従ってこれを選択します。

|関数名|の既定値|
|-------------------|-----------------|
|**mainCRTStartup** (または **wmainCRTStartup**)|/SUBSYSTEM: CONSOLE; を使用するアプリケーション呼び出し `main` (または `wmain` )|
|**WinMainCRTStartup** (または **wWinMainCRTStartup**)|/SUBSYSTEM:**WINDOWS** を使用するアプリケーションを `WinMain` `wWinMain` 使用するために定義する必要がある (または) を呼び出します。 **`__stdcall`**|
|**_DllMainCRTStartup**|DLL。を `DllMain` 使用するように定義する必要がある場合は、を呼び出します。 **`__stdcall`**|

[/Dll](dll-build-a-dll.md)または[/SUBSYSTEM](subsystem-specify-subsystem.md)オプションが指定されていない場合、リンカーはまたはが定義されているかどうかによって、サブシステムとエントリポイントを選択し `main` `WinMain` ます。

、、および関数は、 `main` `WinMain` `DllMain` ユーザー定義のエントリポイントの3つの形式です。

マネージイメージを作成する場合、/ENTRY に指定する関数には、(LPVOID *var1*、DWORD *var2*、lpvoid *var3*) のシグネチャが必要です。

独自のエントリポイントを定義する方法の詳細につい `DllMain` ては、「 [dll and Visual C++ ランタイムライブラリの動作](../run-time-library-behavior.md) 」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **詳細設定** ] プロパティページをクリックします。

1. **エントリポイント** のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
