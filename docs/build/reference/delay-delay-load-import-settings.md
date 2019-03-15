---
title: /DELAY (遅延読み込みのインポート設定)
ms.date: 11/04/2016
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
ms.openlocfilehash: d3c32ba04cbad509ff2819020a35102698d6ceb3
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821340"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (遅延読み込みのインポート設定)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Remarks

/DELAY オプション コントロール[遅延読み込み](linker-support-for-delay-loaded-dlls.md)Dll の。

- UNLOAD 修飾子は、DLL の明示的なアンロードをサポートするように遅延読み込みヘルパー関数に指定します。 インポート アドレス テーブル (IAT) は元の形式にリセットされ、IAT のポインターは無効になって上書きされます。

   すべての呼び出しにアンロードを選択しない場合[FUnloadDelayLoadedDLL](explicitly-unloading-a-delay-loaded-dll.md)は失敗します。

- NOBIND 修飾子は、バインドできる IAT を最終イメージに含めないようにリンカーに指定します。 既定では、遅延読み込みされる DLL に対してバインドできる IAT が作成されます。 生成されるイメージは静的にバインドできません。 (バインドできる IAT を含むイメージは、実行前に静的にバインドできます)。参照してください[/bind](bind.md)します。

   ヘルパー関数が呼び出す代わりに、バインドされた情報を使用しようとして、DLL がバインドされている場合[GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress)各参照されているインポートします。 タイムスタンプまたは優先アドレスが、読み込まれた DLL のものと一致しない場合、ヘルパー関数はバインドされた IAT は古いと見なし、バインドされた IAT が存在しないかのように続行します。

   NOBIND を使用すると、プログラム イメージは大きくなりますが、DLL の読み込み時間は速くなります。 DLL をバインドしない場合は、NOBIND を使用すると、バインドされた IAT は生成されません。

遅延読み込みする Dll を指定するには、使用、 [/DELAYLOAD](delayload-delay-load-import.md)オプション。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 展開**構成プロパティ**、**リンカー**、し、**詳細**します。

1. 変更、 **DLL の遅延読み込み**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
