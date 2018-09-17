---
title: -DLL (DLL のビルド) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dll
dev_langs:
- C++
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec5beed66de3834759f35a5021d0155eab0a066e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716834"
---
# <a name="dll-build-a-dll"></a>/DLL (DLL のビルド)

```
/DLL
```

## <a name="remarks"></a>Remarks

/DLL オプションは、メイン出力ファイルとして DLL をビルドします。 通常、DLL には、別のプログラムで使用できるエクスポートが含まれます。 使用の推奨される順序で、エクスポートを指定するための 3 つの方法はあります。

1. [方式](../../cpp/dllexport-dllimport.md)でソース コード

1. [エクスポート](../../build/reference/exports.md).def ファイル内のステートメント

1. [/Export](../../build/reference/export-exports-a-function.md) LINK コマンド内の指定

プログラムでは、1 つ以上のメソッドを使用できます。

DLL をビルドする別の方法は、**ライブラリ**モジュール定義ステートメント。 /BASE と/DLL オプションはまとめてと同じですが、**ライブラリ**ステートメント。

開発環境以外では、このオプションを指定しません。このオプションは、コマンドラインでのみ使用されます。 アプリケーション ウィザードで DLL プロジェクトを作成するときに、このオプションが設定されます。

.Dll を作成する前に、準備手順で、インポート ライブラリを作成する場合を渡す必要がある同じ一連のオブジェクト ファイル、.dll を作成するときにインポート ライブラリを構築するときに渡されたことに注意してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**構成プロパティ**フォルダー。

1. をクリックして、**全般**プロパティ ページ。

1. 変更、**構成の種類**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)