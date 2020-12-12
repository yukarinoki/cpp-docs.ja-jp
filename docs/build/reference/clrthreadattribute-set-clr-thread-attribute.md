---
description: 詳細情報:/CLRTHREADATTRIBUTE (CLR スレッド属性の設定)
title: /CLRTHREADATTRIBUTE (CLR スレッド属性の設定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: 119797ee10ed0c08477b8e08635605e4299ffd41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179123"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (CLR スレッド属性の設定)

CLR プログラムのエントリポイントのスレッド属性を明示的に指定します。

## <a name="syntax"></a>構文

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>パラメーター

**MTA**<br/>
MTAThreadAttribute 属性をプログラムのエントリポイントに適用します。

**NONE**<br/>
/Clrthreadattributeを指定しない場合と同じです。  共通言語ランタイム (CLR) が既定のスレッド属性を設定できるようにします。

**STA**<br/>
STAThreadAttribute 属性をプログラムのエントリポイントに適用します。

## <a name="remarks"></a>解説

スレッド属性の設定は、.exe をビルドする場合にのみ有効です。これは、メインスレッドのエントリポイントに影響を与えるためです。

既定のエントリポイント (main または wmain など) を使用する場合は、/CLRTHREADATTRIBUTE を使用するか、スレッド属性 (STAThreadAttribute または MTAThreadAttribute) を既定のエントリ関数に配置することによって、スレッドモデルを指定します。

既定以外のエントリポイントを使用する場合は、/CLRTHREADATTRIBUTE を使用するか、スレッド処理属性を既定以外のエントリ関数に配置して、既定以外のエントリポイントを [/entry](entry-entry-point-symbol.md)で指定することによって、スレッドモデルを指定します。

ソースコードに指定されているスレッドモデルが、/CLRTHREADATTRIBUTE で指定されたスレッドモデルに一致しない場合、リンカーは/CLRTHREADATTRIBUTE を無視し、ソースコードで指定されたスレッドモデルを適用します。

シングルスレッドを使用する必要があるのは、CLR プログラムがシングルスレッドを使用する COM オブジェクトをホストしている場合などです。  CLR プログラムがマルチスレッドを使用する場合、シングルスレッドを使用する COM オブジェクトをホストすることはできません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. **[リンカー]** ノードを展開します。

1. **[詳細]** プロパティ ページを選択します。

1. **CLR スレッド属性** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
