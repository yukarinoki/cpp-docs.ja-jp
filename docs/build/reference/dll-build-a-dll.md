---
description: 詳細情報:/DLL (DLL のビルド)
title: /DLL (DLL のビルド)
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: 42535fb15762e5c0f1691d5c28029c7368005f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201405"
---
# <a name="dll-build-a-dll"></a>/DLL (DLL のビルド)

```
/DLL
```

## <a name="remarks"></a>解説

/DLL オプションは、メインの出力ファイルとして DLL をビルドします。 DLL には、通常、別のプログラムで使用できるエクスポートが含まれています。 エクスポートを指定するには、次の3つの方法を使用することをお勧めします。

1. ソースコード内の[__declspec (dllexport)](../../cpp/dllexport-dllimport.md)

1. .Def ファイル内の [エクスポート](exports.md) ステートメント

1. リンクコマンドでの [/export](export-exports-a-function.md) の指定

プログラムでは、複数のメソッドを使用できます。

DLL をビルドするもう1つの方法は、 **ライブラリ** のモジュール定義ステートメントを使用することです。 /BASE オプションと/DLL オプションを一緒に使うことは、 **LIBRARY** ステートメントと同じです。

開発環境では、このオプションを指定しないでください。このオプションは、コマンドラインでのみ使用します。 このオプションは、アプリケーションウィザードを使用して DLL プロジェクトを作成するときに設定されます。

準備手順でインポートライブラリを作成する場合は、.dll を作成する前に、.dll をビルドするときに、インポートライブラリのビルド時に渡されたものと同じオブジェクトファイルのセットを渡す必要があることに注意してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成プロパティ** ] フォルダーをクリックします。

1. [ **全般** ] プロパティページをクリックします。

1. " **構成の種類** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
