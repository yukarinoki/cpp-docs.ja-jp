---
title: バージョン情報リソース (C++) の文字列の編集
ms.date: 11/04/2016
f1_keywords:
- vc.editors.version
helpviewer_keywords:
- version information resources [C++]
- resources [C++], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
ms.openlocfilehash: 75d41444d685b067b57aa78aee944ee005da5d3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476428"
---
# <a name="editing-a-string-in-a-version-information-resource-c"></a>バージョン情報リソース (C++) の文字列の編集

### <a name="to-edit-a-string-in-a-version-information-resource"></a>バージョン情報リソースの文字列を編集するには

1. 1 回アイテムをクリックして選択し、もう一度クリックして編集を開始します。 変更を直接、**バージョン情報**テーブルまたは、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 加えた変更は、両方の場所で反映されます。

   > [!NOTE]
   > 編集するときに、`FILEFLAGS`キー、**バージョン情報**エディター、わかります設定することはできません、**デバッグ**、**プライベート ビルド**、または**特別なビルド**プロパティ (で、**プロパティ**ウィンドウ) .rc ファイル。

   - **バージョン情報**エディター セット、**デバッグ**プロパティを`#ifdef`、リソース スクリプトに基づく、`_DEBUG`ビルド フラグ。

   - 場合、`Private Build`キーには、**値**設定、**バージョン情報**テーブルを対応する**プライベート ビルド**プロパティ (で、**プロパティ**ウィンドウ) の`FILEFLAGS`鍵となる**True**します。 **値** が空の場合、プロパティは **False**になります。 同様に、**特殊ビルド**キー (で、**バージョン情報**テーブル) に関連付けられている、**特殊ビルド**プロパティを`FILEFLAGS`キー。

キーまたは値の列見出しをクリックすることにより、文字列ブロックの情報シーケンスをソートすることができます。 これらの見出しは、選択した順序に情報を自動的に再配置します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[バージョン エディター](../windows/version-information-editor.md)<br/>
[バージョン情報 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)