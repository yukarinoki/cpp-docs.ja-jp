---
title: /CLRUNMANAGEDCODECHECK (削除 SuppressUnmanagedCodeSecurityAttribute) |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
dev_langs:
- C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9868f0c35f4a988ac8e0aee8076f232f86c04afd
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820926"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (削除 SuppressUnmanagedCodeSecurityAttribute)

**/CLRUNMANAGEDCODECHECK**リンカーが適用されないことを指定します。<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>リンカーによって生成されたに`PInvoke`マネージ コードからネイティブ Dll への呼び出し。

## <a name="syntax"></a>構文

> **/CLRUNMANAGEDCODECHECK****[: NO]**

## <a name="remarks"></a>Remarks

既定では、リンカーが適用されます、 **SuppressUnmanagedCodeSecurityAttribute**リンカーによって生成されたに`PInvoke`呼び出し。 ときに **/CLRUNMANAGEDCODECHECK**が有効で**SuppressUnmanagedCodeSecurityAttribute**が削除されます。 明示的に適用する、 **SuppressUnmanagedCodeSecurityAttribute**リンカーによって生成されたに`PInvoke`呼び出しが使用できる **/CLRUNMANAGEDCODECHECK:NO**します。

リンカーは、使用してコンパイルされたオブジェクトに属性を追加するだけ **/clr**または **/clr: 純粋な**します。 ただし、 **/clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

A`PInvoke`リンカーは、マネージ呼び出し元からの参照を満たすためにマネージ シンボルを見つけることができませんが、その参照を満たすためにネイティブのシンボルを検索できる場合に呼び出しがリンカーによって生成されます。 詳細については`PInvoke`を参照してください[マネージ コードからネイティブ関数の呼び出し](../../dotnet/calling-native-functions-from-managed-code.md)します。

使用する場合に注意する<xref:System.Security.AllowPartiallyTrustedCallersAttribute>、コードにする必要があります明示的に設定する **/CLRUNMANAGEDCODECHECK**を削除する、 **SuppressUnmanagedCodeSecurity**属性。 イメージには、両方が含まれている場合は、潜在的なセキュリティの脆弱性、 **SuppressUnmanagedCodeSecurity**と**AllowPartiallyTrustedCallers**属性。

参照してください[アンマネージ コードのコーディング ガイドラインをセキュリティで保護された](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code)を使用する影響の詳細については**SuppressUnmanagedCodeSecurityAttribute**します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**リンカー**ノード。

1. 選択、**詳細**プロパティ ページ。

1. 変更、 **CLR アンマネージド コード チェック**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)
