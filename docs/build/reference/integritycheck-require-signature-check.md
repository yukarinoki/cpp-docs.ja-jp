---
title: /INTEGRITYCHECK (シグネチャ確認が必要)
ms.date: 11/04/2016
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
ms.openlocfilehash: 8530175cd5bc0ed5dced7f92e5f67a1576bb43e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578348"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (シグネチャ確認が必要)

読み込み時にバイナリ イメージのデジタル署名を確認する必要があることを指定します。

```
/INTEGRITYCHECK[:NO]
```

## <a name="remarks"></a>Remarks

既定では、 **/INTEGRITYCHECK**はオフです。

**/INTEGRITYCHECK**オプション セット — DLL ファイルまたは実行可能ファイルの PE ヘッダーに、メモリ マネージャーは、Windows でイメージを読み込むために、デジタル署名の確認に使用するフラグ。 このオプションは、特定の Windows 機能によって読み込まれるカーネル モード コードを実装する 32 ビットと 64 ビットの両方の Dll に対して設定する必要がありますは、Windows Vista、Windows 7、Windows 8、Windows Server 2008、および Windows Server 2012 上のすべてのデバイス ドライバーをお勧めします。 Windows Vista 以前の Windows は、このフラグを無視します。 詳細については、次を参照してください。[強制整合性の署名のポータブル実行可能ファイル (PE) ファイル](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)します。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**リンカー**ノード。

1. 選択、**コマンドライン**プロパティ ページ。

1. **追加オプション**、入力`/INTEGRITYCHECK`または`/INTEGRITYCHECK:NO`します。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
[強制の整合性の署名のポータブル実行可能ファイル (PE) ファイル](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)<br/>
[カーネル モード コード署名のチュートリアル](https://msdn.microsoft.com/windows/hardware/gg487328.aspx)<br/>
[Windows 7 および Windows Server 2008 での AppInit Dll](https://msdn.microsoft.com/windows/hardware/gg463040.aspx)