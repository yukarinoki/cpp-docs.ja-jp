---
description: 詳細情報:/DELAY (遅延読み込みのインポート設定)
title: /DELAY (遅延読み込みのインポート設定)
ms.date: 01/28/2021
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
ms.openlocfilehash: 0dd6aaaffd378afe4ca7d75180da869b2748d639
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522197"
---
# <a name="delay-delay-load-import-settings"></a>`/DELAY` (遅延読み込みのインポート設定)

リンカーオプション。実行時の Dll の遅延読み込みを制御します。

## <a name="syntax"></a>構文

> **`/DELAY:UNLOAD`**\
> **`/DELAY:NOBIND`**

## <a name="remarks"></a>解説

オプションは、 **`/DELAY`** dll の [遅延読み込み](linker-support-for-delay-loaded-dlls.md) を制御します。

- 修飾子は、 **`/DELAY:UNLOAD`** DLL の明示的なアンロードをサポートするように遅延読み込みヘルパー関数を示します。 インポート アドレス テーブル (IAT) は元の形式にリセットされ、IAT のポインターは無効になって上書きされます。

   を選択しない場合 **`/DELAY:UNLOAD`** 、の呼び出し [`__FUnloadDelayLoadedDLL`](linker-support-for-delay-loaded-dlls.md#explicitly-unload-a-delay-loaded-dll) は失敗します。

- 修飾子は、 **`/DELAY:NOBIND`** バインド可能な IAT を最終イメージに含めないようにリンカーに指示します。 既定では、遅延読み込みされる DLL に対してバインドできる IAT が作成されます。 生成されたイメージを静的にバインドすることはできません。 (バインド可能な IATs を含むイメージは、実行前に静的にバインドされる場合があります)。詳細については、「」を参照してください [`/BIND`](bind.md) 。

   DLL がバインドされている場合、ヘルパー関数は、参照される各インポートでを呼び出すのではなく、バインドされた情報を使用しようとし [`GetProcAddress`](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) ます。 タイムスタンプまたは優先するアドレスが、読み込まれている DLL 内のアドレスと一致しない場合、ヘルパー関数はバインドされた IAT が古くなっているものと見なします。 バインドされた IAT が存在しない場合と同様に続行されます。

   **`/DELAY:NOBIND`** プログラムイメージのサイズを大きくしますが、DLL の読み込み時間を短縮することができます。 DLL をバインドしない場合は、バインドされ **`/DELAY:NOBIND`** た IAT が生成されないようにします。

読み込みを遅延させる Dll を指定するには、オプションを使用し [`/DELAYLOAD`](delayload-delay-load-import.md) ます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual Studio での C++ コンパイラとビルドプロパティの設定](../working-with-project-properties.md)」を参照してください。

1. [**構成プロパティ**]  >  **リンカー** の  >  **[詳細設定**] プロパティページを選択します。

1. **遅延読み込み DLL** プロパティを変更します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーリファレンス](linking.md)\
[MSVC リンカー オプション](linker-options.md)
