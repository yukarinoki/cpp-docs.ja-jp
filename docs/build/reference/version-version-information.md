---
description: 詳細について:/VERSION (バージョン情報)
title: /VERSION (バージョン情報)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 7c6a27e4829c4acf66db2887e01a147aceb1c5d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176367"
---
# <a name="version-version-information"></a>/VERSION (バージョン情報)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>引数

*メジャー* と *マイナー*<br/>
.Exe ファイルまたは .dll ファイルのヘッダーに必要なバージョン番号。

## <a name="remarks"></a>解説

/VERSION オプションは、.exe ファイルまたは .dll ファイルのヘッダーにバージョン番号を配置するようにリンカーに指示します。 /Versionの効果を確認するには、DUMPBIN [/ヘッダー](headers.md) を使用して、オプションのヘッダー値の image version フィールドを表示します。

*Major* および *minor* 引数は、0 ~ 65535 の範囲の10進数です。 既定値は、バージョン0.0 です。

/VERSION で指定された情報は、エクスプローラーでプロパティを表示するときに、アプリケーションに対して表示されるバージョン情報には影響しません。 このバージョン情報は、アプリケーションのビルドに使用されるリソースファイルから取得されます。 詳細については、「 [バージョン情報エディター](../../windows/version-information-editor.md) 」を参照してください。

バージョン番号を挿入するもう1つの方法として、 [バージョン](version-c-cpp.md) のモジュール定義ステートメントがあります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **全般** ] プロパティページをクリックします。

1. **Version** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
