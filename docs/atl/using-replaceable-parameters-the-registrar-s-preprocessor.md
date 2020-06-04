---
title: 置き換え可能パラメーターの使用 (ATL レジストラー)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: debbccea5836fa63282b62ff87573160069fb169
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168684"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>置き換え可能パラメーターの使用 (レジストラー&#39;s プリプロセッサ)

置き換え可能パラメーターを使用すると、レジストラーのクライアントは実行時のデータを指定できます。 これを行うために、レジストラーは、スクリプト内の置き換え可能パラメーターに関連付けられた値を入力する置換マップを保持します。 レジストラーは、これらのエントリを実行時に作成します。

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a>% MODULE% を使用しています

[ATL コントロールウィザード](../atl/reference/atl-control-wizard.md)では、を使用`%MODULE%`するスクリプトが自動的に生成されます。 ATL では、この置き換え可能なパラメーターをサーバーの DLL または EXE の実際の場所として使用します。

## <a name="concatenating-run-time-data-with-script-data"></a>実行時データとスクリプトデータの連結

プリプロセッサのもう1つの使用方法として、実行時データをスクリプトデータと連結する方法があります。 たとえば、末尾に "`, 1`" という文字列が追加されたモジュールへの完全なパスを含むエントリが必要であるとします。 まず、次の拡張を定義します。

```rgs
'MySampleKey' = s '%MODULE%, 1'
```

次に、「[スクリプトの呼び出し](../atl/invoking-scripts.md)」に一覧表示されているスクリプト処理メソッドの1つを呼び出す前に、置換をマップに追加します。

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

スクリプトの解析中、レジストラーはに`'%MODULE%, 1'` `c:\mycode\mydll.dll, 1`展開されます。

> [!NOTE]
> レジストラースクリプトでは、4K は最大トークンサイズです。 (トークンは、構文内で認識可能な要素です)。これには、プリプロセッサによって作成または展開されたトークンが含まれます。

> [!NOTE]
> 実行時に置換値を置き換えるには、スクリプト内の呼び出しを[DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource)または[DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid)マクロに削除します。 代わりに、 [CAtlModule:: UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced)また`UpdateRegistry`は[CAtlModule:: UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources)を呼び出す独自のメソッドで置き換え、_ATL_REGMAP_ENTRY 構造体の配列を渡します。 _ATL_REGMAP_ENTRY の配列には、{NULL, NULL} に設定されているエントリが少なくとも1つ必要です。また、このエントリは常に最後のエントリにする必要があります。 それ以外の場合は、が呼び出されると`UpdateRegistryFromResource` 、アクセス違反エラーが生成されます。

> [!NOTE]
> 実行可能ファイルを出力するプロジェクトをビルドすると、実行時に作成されたパス名を示す引用符が ATL によって **% MODULE%** レジストラースクリプトパラメーターと共に自動的に追加されます。 パス名に引用符を含めたくない場合は、代わりに新しい **% MODULE_RAW%** パラメーターを使用してください。
>
> DLL を出力するプロジェクトをビルドするときに、 **% MODULE%** または **% MODULE_RAW%** が使用されている場合、ATL はパス名に引用符を追加しません。

## <a name="see-also"></a>関連項目

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
