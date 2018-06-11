---
title: /DEFAULTLIB (既定のライブラリの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs:
- C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9afcaa0e229ec34ba91b4d60a7a4fa9acec2d7e3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569782"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (既定のライブラリの指定)

外部参照を解決するのには検索する既定のライブラリを指定します。

## <a name="syntax"></a>構文

> **/DEFAULTLIB**:_ライブラリ_

### <a name="arguments"></a>引数

|引数|説明|
|-|-|
*ライブラリ*|外部参照を解決するときに検索するライブラリの名前。

## <a name="remarks"></a>コメント

**/DEFAULTLIB**オプションでは、1 つ追加*ライブラリ*リンク参照の解決時に検索するライブラリの一覧にします。 指定されたライブラリ **/DEFAULTLIB**後、コマンドラインでと .obj ファイル内の既定のライブラリの前に明示的に指定されたライブラリを検索します。

引数を指定せずに使用する場合、 [/NODEFAULTLIB (すべて既定のライブラリの無視)](../../build/reference/nodefaultlib-ignore-libraries.md)オプションはすべて、オーバーライド **/DEFAULTLIB**:*ライブラリ*オプション。 **/NODEFAULTLIB**:*ライブラリ*オプションにより **/DEFAULTLIB**:*ライブラリ*とき同じ*ライブラリ*両方の名前を指定します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. **追加オプション**、入力、 **/DEFAULTLIB**:*ライブラリ*を検索するには、各ライブラリのオプションです。 選択**OK**して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)
