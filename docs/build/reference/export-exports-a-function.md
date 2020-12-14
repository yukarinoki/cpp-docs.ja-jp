---
description: 詳細情報:/EXPORT (関数のエクスポート)
title: /EXPORT (関数のエクスポート)
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
ms.openlocfilehash: a52ea79d0569d31c26eabd06d51ef58a10567119
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200807"
---
# <a name="export-exports-a-function"></a>/EXPORT (関数のエクスポート)

関数を名前または序数 (またはデータ) でプログラムからエクスポートします。

## <a name="syntax"></a>構文

> **/Export:**<em>entryname</em>[**, \@**<em>ordinal</em>[**,**]] [**, DATA**]

## <a name="remarks"></a>解説

**/Export** オプションは、プログラムからエクスポートする関数またはデータ項目を指定します。これにより、他のプログラムが関数を呼び出したり、データを使用したりできるようになります。 通常、エクスポートは DLL で定義されます。

*Entryname* は、呼び出し元のプログラムによって使用される関数またはデータ項目の名前です。 *序数* 1 ~ 65535 の範囲で、エクスポートテーブルのインデックスを指定します。 *序数* を指定しない場合、LINK は1を割り当てます。 Entryname **キーワードを** 使用すると、関数は序数としてのみエクスポートされます。

**Data** キーワードは、エクスポートされたアイテムがデータアイテムであることを指定します。 クライアントプログラムのデータ項目は、 **extern __declspec (dllimport)** を使用して宣言する必要があります。

定義をエクスポートするには、次の4つの方法を使用することをお勧めします。

1. ソースコード内の[__declspec (dllexport)](../../cpp/dllexport-dllimport.md)

1. .Def ファイル内の [エクスポート](exports.md) ステートメント

1. LINK コマンドでの /EXPORT の指定

1. ソースコード内のの形式の [コメント](../../preprocessor/comment-c-cpp.md) ディレクティブ `#pragma comment(linker, "/export: definition ")` 。

これらのメソッドはすべて、同じプログラムで使用できます。 リンクがエクスポートを含むプログラムをビルドする場合、ビルドで .exp ファイルが使用されていない限り、インポートライブラリも作成されます。

リンクは、修飾形式の識別子を使用します。 コンパイラは、.obj ファイルを作成するときに識別子を装飾します。 *Entryname* が、ソースコードに示されているように、非装飾形式でリンカーに指定されている場合、リンクは名前と一致するように試みます。 一意の一致が見つからない場合は、リンクによってエラーメッセージが表示されます。 [DUMPBIN](dumpbin-reference.md)ツールを使用して、識別子をリンカーに指定する必要がある場合に、[修飾名](decorated-names.md)の形式を取得します。

> [!NOTE]
> **`__cdecl`** またはとして宣言されている C 識別子の装飾形式を指定しないでください **`__stdcall`** 。

修飾されていない関数名をエクスポートする必要があり、ビルド構成 (たとえば、32ビットまたは64ビットのビルド) によって異なるエクスポートがある場合は、構成ごとに異なる DEF ファイルを使用できます。 (プリプロセッサの条件付きディレクティブは DEF ファイルでは使用できません)。代わりに、次に示すように、 `#pragma comment` 関数宣言の前にディレクティブを使用することもできます。ここで、は非 `PlainFuncName` 装飾名、 `_PlainFuncName@4` は関数の装飾名です。

```cpp
#pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
BOOL CALLBACK PlainFuncName( Things * lpParams)
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. [ **追加オプション** ] ボックスにオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
