---
title: 置き換え可能パラメーターの使用 (ATL レジストラー)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 2474db2de384baa9113ed39aef4d3d9c9048903d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329229"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>置き換え可能パラメーターの使用 (レジストラー&#39;s プリプロセッサ)

置き換え可能パラメーターを使用すると、レジストラーのクライアントは実行時データを指定できます。 これを行うために、レジストラーは置換マップを維持し、スクリプト内の置き換え可能なパラメータに関連付けられた値を入力します。 レジストラーは、実行時にこれらのエントリを作成します。

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a>%モジュール% を使用しています

[ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)は、 を使用`%MODULE%`するスクリプトを自動的に生成します。 ATL は、サーバーの DLL または EXE の実際の場所に、この置き換え可能なパラメータを使用します。

## <a name="concatenating-run-time-data-with-script-data"></a>ランタイム データとスクリプト データの連結

プリプロセッサのもう 1 つの用途は、実行時データとスクリプト データを連結することです。 たとえば、末尾に文字列 " " を`, 1`付加したモジュールへの完全パスを含むエントリが必要であるとします。 まず、次の展開を定義します。

```
'MySampleKey' = s '%MODULE%, 1'
```

次に、「スクリプトの呼び出し」にリストされているスクリプト処理メソッドのいずれかを[呼び出す前に](../atl/invoking-scripts.md)、マップに置き換えを追加します。

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

スクリプトの解析中に、レジストラーは`'%MODULE%, 1'`に展開されます。 `c:\mycode\mydll.dll, 1`

> [!NOTE]
> レジストラー スクリプトでは、4K はトークンの最大サイズです。 (トークンは構文内の認識可能な要素です。これには、プリプロセッサによって作成または展開されたトークンが含まれます。

> [!NOTE]
> 実行時に置換値を置き換える場合は、スクリプト内の呼び出しを[DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource)または[マクロに削除DECLARE_REGISTRY_RESOURCEID。](../atl/reference/registry-macros.md#declare_registry_resourceid) 代わりに`UpdateRegistry`[、CAtlModule:::更新レジストリからリソースまたは](../atl/reference/catlmodule-class.md#updateregistryfromresourced)[CAtlModule:::_ATL_REGMAP_ENTRY](../atl/reference/catlmodule-class.md#updateregistryfromresources)構造体の配列を渡す独自のメソッドに置き換えます。 _ATL_REGMAP_ENTRYの配列には、{NULL,NULL} に設定されたエントリが少なくとも 1 つ必要です。 それ以外の場合は、呼び出されたときに`UpdateRegistryFromResource`アクセス違反エラーが生成されます。

> [!NOTE]
> 実行可能ファイルを出力するプロジェクトをビルドする場合、ATL は実行時に作成されたパス名を引用符で囲み、実行時に **%MODULE%** レジストラ スクリプト パラメーターを使用して自動的に追加します。 パス名に引用符を含めたくない場合は、代わりに新しい **%MODULE_RAW%** パラメーターを使用してください。
>
> DLL を出力するプロジェクトをビルドする場合 **、%MODULE%** または **%MODULE_RAW%** が使用されている場合、ATL はパス名に引用符を追加しません。

## <a name="see-also"></a>関連項目

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
