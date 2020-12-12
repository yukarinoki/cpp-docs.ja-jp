---
description: 詳細情報:/APPCONTAINER (Microsoft Store アプリ)
title: /APPCONTAINER (UWP/Microsoft Store アプリ)
ms.date: 11/04/2016
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
ms.openlocfilehash: 4cb78c85aa59ebd7fc0eb82af9497606bc3c431c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179578"
---
# <a name="appcontainer-microsoft-store-app"></a>/APPCONTAINER (Microsoft Store アプリ)

リンカーがアプリ コンテナーで実行される必要がある実行可能イメージを生成するかどうかを指定します。

## <a name="syntax"></a>構文

```
/APPCONTAINER[:NO]
```

## <a name="remarks"></a>解説

既定では、/APPCONTAINER は無効になっています。

このオプションは、実行可能ファイルを変更し、appcontainer プロセス分離環境でアプリが実行される必要があるかどうかを示します。 Appcontainer 環境で実行する必要があるアプリの場合は、たとえば、ユニバーサル Windows プラットフォーム (UWP) アプリや Windows Phone 2.x アプリなどを指定します。 (テンプレートからユニバーサル Windows アプリを作成すると、Visual Studio でオプションが自動的に設定されます)。デスクトップアプリの場合は、[/APPCONTAINER: いいえ] を指定するか、オプションを省略します。

/APPCONTAINER オプションは Windows 8 で導入されました。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. **[構成プロパティ]** ノードを展開します。

1. **[リンカー]** ノードを展開します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション**] で、またはを入力し `/APPCONTAINER` `/APPCONTAINER:NO` ます。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
