---
title: スクリプト (ATL) の呼び出し
ms.date: 11/04/2016
f1_keywords:
- StringRegister
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 170eb4c29571fcec8797727f54630894c9198442
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650555"
---
# <a name="invoking-scripts"></a>スクリプトの呼び出し

[置き換え可能パラメーター (、レジストラー プリプロセッサ) を使用して](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)置換マップをについて説明し、レジストラー メソッドをメンション**AddReplacement**します。 レジストラーが、スクリプトに固有の他の 8 つのメソッドと、すべては、次の表で説明します。

|メソッド|構文/説明|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resFileName* **、UINT** `nID` **、LPCOLESTR** `szType` **)。**<br /><br /> モジュールのリソースに含まれるスクリプトを登録します。 *resFileName*モジュール自体への UNC パスを示します。 *nID*と*szType*リソースの ID と型をそれぞれが含まれます。|
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***resFileName* **、UINT** `nID` **、LPCOLESTR** `szType` **)。**<br /><br /> モジュールのリソースに含まれるスクリプトを登録解除します。 *resFileName*モジュール自体への UNC パスを示します。 *nID*と*szType*リソースの ID と型をそれぞれが含まれます。|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **、LPCOLESTR***szID* **、LPCOLESTR** `szType`**);**<br /><br /> モジュールのリソースに含まれるスクリプトを登録します。 *resFileName*モジュール自体への UNC パスを示します。 *szID*と*szType*リソースの文字列識別子と型をそれぞれが含まれます。|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **、LPCOLESTR***szID* **、LPCOLESTR** `szType` **);**<br /><br /> モジュールのリソースに含まれるスクリプトを登録解除します。 *resFileName*モジュール自体への UNC パスを示します。 *szID*と*szType*リソースの文字列識別子と型をそれぞれが含まれます。|
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR***fileName***)。**<br /><br /> ファイルにスクリプトを登録します。 *ファイル名*が含まれています (または) リソース スクリプト ファイルを UNC パスです。|
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR***fileName***)。**<br /><br /> ファイル内のスクリプトを登録解除します。 *ファイル名*が含まれています (または) リソース スクリプト ファイルを UNC パスです。|
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR***データ***)。**<br /><br /> 文字列内のスクリプトを登録します。 *データ*スクリプト自体が含まれています。|
|**StringUnregister**|**HRESULT StringUnregister (LPCOLESTR***データ***)。**<br /><br /> 文字列内のスクリプトを登録解除します。 *データ*スクリプト自体が含まれています。|

**ResourceRegisterSz**と**ResourceUnregisterSz**のような**ResourceRegister**と**ResourceUnregister**が文字列を指定することができます識別子です。

メソッド**FileRegister**と**FileUnregister**は、リソース スクリプトしたくない場合、または独自のファイルでスクリプトの場合に役立ちます。 メソッド**StringRegister**と**StringUnregister** .rgs ファイルが動的に割り当てられた文字列に格納します。

## <a name="see-also"></a>関連項目

[レジストラー スクリプトの作成](../atl/creating-registrar-scripts.md)

