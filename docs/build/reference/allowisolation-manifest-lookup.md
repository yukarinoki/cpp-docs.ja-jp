---
description: 詳細情報:/自動 (マニフェスト参照)
title: /ALLOWISOLATION (マニフェスト検索)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: 659c908e4de910941ca71c9f40814608df19c6d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187222"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (マニフェスト検索)

マニフェスト検索の動作を指定します。

## <a name="syntax"></a>構文

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>解説

または、[**いいえ**] に設定すると、マニフェストがないかのように dll が読み込まれ、リンカーによって `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` オプションのヘッダーのフィールドにビットが設定され `DllCharacteristics` ます。

また、オペレーティングシステムはマニフェストの参照と読み込みを実行します。

これ **が既定値です。**

実行可能ファイルの分離が無効になっている場合、Windows ローダーは、新しく作成されたプロセスのアプリケーションマニフェストの検索を試行しません。 新しいプロセスには、実行可能ファイル内にマニフェストがある場合や、実行可能ファイルと <em>いう名前の</em>実行可能ファイルと同じディレクトリに配置されている場合でも、既定のアクティベーションコンテキストがありませ **ん。**

詳細については、「 [マニフェストファイルリファレンス](/windows/win32/SbsCs/manifest-files-reference)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **マニフェストファイル**] プロパティページを選択します。

1. " **分離を許可する** " プロパティを変更します。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
