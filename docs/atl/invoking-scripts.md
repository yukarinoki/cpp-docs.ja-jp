---
description: '詳細情報: スクリプトの呼び出し'
title: スクリプトの呼び出し (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 48fc49118d93893b5cd60462fbaecfdb73d747c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152660"
---
# <a name="invoking-scripts"></a>スクリプトの呼び出し

[置き換え可能パラメーター (レジストラーのプリプロセッサ) を使用して](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 、置換マップについて説明し、レジストラーメソッド **addreplacement** を紹介します。 レジストラーには、スクリプトに固有の他の8つのメソッドがあり、次の表ですべての方法を説明しています。

|Method|構文/説明|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resfilename* **, UINT** `nID` **, LPCOLESTR** `szType` **);**      <br /><br /> モジュールのリソースに格納されているスクリプトを登録します。 *Resfilename* は、モジュール自体への UNC パスを示します。 *nID* と *sztype* には、それぞれリソースの ID と種類が含まれています。|
|**ResourceUnregister 解除**|**HRESULT resourceunregister 登録解除 (LPCOLESTR***resfilename* **, UINT** `nID` **, LPCOLESTR** `szType` **);**      <br /><br /> モジュールのリソースに含まれているスクリプトの登録を解除します。 *Resfilename* は、モジュール自体への UNC パスを示します。 *nID* と *sztype* には、それぞれリソースの ID と種類が含まれています。|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resfilename* **、LPCOLESTR***szid* **、LPCOLESTR** `szType` **);**      <br /><br /> モジュールのリソースに格納されているスクリプトを登録します。 *Resfilename* は、モジュール自体への UNC パスを示します。 *Szid* と *szid* には、それぞれリソースの文字列識別子と型が含まれています。|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resfilename* **、LPCOLESTR***szid* **、LPCOLESTR** `szType` **);**      <br /><br /> モジュールのリソースに含まれているスクリプトの登録を解除します。 *Resfilename* は、モジュール自体への UNC パスを示します。 *Szid* と *szid* には、それぞれリソースの文字列識別子と型が含まれています。|
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR**  *fileName*  **);**<br /><br /> スクリプトをファイルに登録します。 *fileName* は、リソーススクリプトを含む (または) ファイルへの UNC パスです。|
|**FileUnregister 解除**|**HRESULT FileUnregister 解除 (LPCOLESTR**  *fileName*  **);**<br /><br /> ファイル内のスクリプトの登録を解除します。 *fileName* は、リソーススクリプトを含む (または) ファイルへの UNC パスです。|
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR**  *data*  **);**<br /><br /> スクリプトを文字列に登録します。 *データ* には、スクリプト自体が含まれています。|
|**StringUnregister 解除**|**HRESULT StringUnregister 登録解除 (LPCOLESTR**  *data*  **);**<br /><br /> スクリプトを文字列で登録解除します。 *データ* には、スクリプト自体が含まれています。|

**ResourceRegisterSz** と **Resourceunregistersz** は、 **ResourceRegister** と **resourceの登録解除** に似ていますが、文字列識別子を指定することができます。

**FileRegister** メソッドと **fileunregister 解除** メソッドは、リソース内にスクリプトを作成したくない場合や、スクリプトが独自のファイルに必要な場合に便利です。 **Stringregister** メソッドと **stringregister** メソッドを使用すると、.rgs ファイルを動的に割り当てられた文字列に格納できます。

## <a name="see-also"></a>関連項目

[レジストラースクリプトの作成](../atl/creating-registrar-scripts.md)
