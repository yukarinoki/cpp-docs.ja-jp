---
title: _com_error クラス
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: ace3ac33e4dccd66c0a44095533d657e32b15f1c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837815"
---
# <a name="_com_error-class"></a>_com_error クラス

**Microsoft 固有の仕様**

**_Com_error**オブジェクトは、タイプライブラリから生成されたヘッダーファイル内のエラー処理ラッパー関数、またはいずれかの com サポートクラスによって検出された例外条件を表します。 **_Com_error**クラスは、HRESULT エラーコードおよび関連付けられているオブジェクトをカプセル化し `IErrorInfo Interface` ます。

### <a name="construction"></a>建設

| 名前 | 説明 |
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|**_Com_error**オブジェクトを構築します。|

### <a name="operators"></a>演算子

| 名前 | 説明 |
|-|-|
|[operator =](../cpp/com-error-operator-equal.md)|既存の **_com_error** オブジェクトを別のオブジェクトに割り当てます。|

### <a name="extractor-functions"></a>抽出関数

| 名前 | 説明 |
|-|-|
|[Error](../cpp/com-error-error.md)|コンストラクターに渡された HRESULT を取得します。|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。|
|[WCode](../cpp/com-error-wcode.md)|カプセル化された HRESULT にマップされた16ビットエラーコードを取得します。|

### <a name="ierrorinfo-functions"></a>IErrorInfo の関数

| 名前 | 説明 |
|-|-|
|[説明](../cpp/com-error-description.md)|`IErrorInfo::GetDescription` 関数を呼び出します。|
|[HelpContext](../cpp/com-error-helpcontext.md)|`IErrorInfo::GetHelpContext` 関数を呼び出します。|
|[ヘルプ](../cpp/com-error-helpfile.md)|`IErrorInfo::GetHelpFile` 関数を呼び出します。|
|[ソース](../cpp/com-error-source.md)|`IErrorInfo::GetSource` 関数を呼び出します。|
|[GUID](../cpp/com-error-guid.md)|`IErrorInfo::GetGUID` 関数を呼び出します。|

### <a name="format-message-extractor"></a>書式メッセージの抽出

| 名前 | 説明 |
|-|-|
|[ErrorMessage](../cpp/com-error-errormessage.md)|**_Com_error**オブジェクトに格納されている HRESULT の文字列メッセージを取得します。|

### <a name="exepinfowcode-to-hresult-mappers"></a>ExepInfo.wCode と HRESULT のマッパー

| 名前 | 説明 |
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32ビットの HRESULT を16ビットにマップ `wCode` します。|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16ビット `wCode` を32ビット HRESULT にマップします。|

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>必要条件

**ヘッダー:**\<comdef.h>

`Lib:` (詳細については、「 [/zc: wchar_t (Wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>関連項目

[コンパイラ COM サポートクラス](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo インターフェイス](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)
