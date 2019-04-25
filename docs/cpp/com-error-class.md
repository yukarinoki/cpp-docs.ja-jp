---
title: _com_error クラス
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 8ed1521cbf768e5b473281e5f9b7c6597cdc4692
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155203"
---
# <a name="comerror-class"></a>_com_error クラス

**Microsoft 固有の仕様**

A **_com_error**オブジェクトは、タイプ ライブラリから生成されたヘッダー ファイル内のエラー処理ラッパー関数によって、または COM サポート クラスのいずれかで検出された例外条件を表します。 **_Com_error** HRESULT エラー コードおよび関連クラスがカプセル化`IErrorInfo Interface`オブジェクト。

### <a name="construction"></a>構築

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|構築、 **_com_error**オブジェクト。|

### <a name="operators"></a>演算子

|||
|-|-|
|[operator=](../cpp/com-error-operator-equal.md)|既存 **_com_error**を別のオブジェクト。|

### <a name="extractor-functions"></a>抽出関数

|||
|-|-|
|[Error](../cpp/com-error-error.md)|コンス トラクターに渡された HRESULT を取得します。|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。|
|[WCode](../cpp/com-error-wcode.md)|カプセル化された HRESULT にマップされた 16 ビット エラー コードを取得します。|

### <a name="ierrorinfo-functions"></a>IErrorInfo の関数

|||
|-|-|
|[説明](../cpp/com-error-description.md)|`IErrorInfo::GetDescription` 関数を呼び出します。|
|[HelpContext](../cpp/com-error-helpcontext.md)|`IErrorInfo::GetHelpContext` 関数を呼び出します。|
|[HelpFile](../cpp/com-error-helpfile.md)|`IErrorInfo::GetHelpFile` 関数を呼び出します。|
|[ソース](../cpp/com-error-source.md)|`IErrorInfo::GetSource` 関数を呼び出します。|
|[GUID](../cpp/com-error-guid.md)|`IErrorInfo::GetGUID` 関数を呼び出します。|

### <a name="format-message-extractor"></a>書式メッセージの抽出

|||
|-|-|
|[エラー メッセージ](../cpp/com-error-errormessage.md)|格納された HRESULT の文字列メッセージを取得、 **_com_error**オブジェクト。|

### <a name="exepinfowcode-to-hresult-mappers"></a>ExepInfo.wCode と HRESULT のマッパー

|||
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|16 ビットに 32 ビットの HRESULT をマップ`wCode`します。|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16 ビット マップ`wCode`HRESULT の 32 ビットにします。|

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>必要条件

**ヘッダー:** \<comdef.h >

`Lib:` comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)

## <a name="see-also"></a>関連項目

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo インターフェイス](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)