---
title: _com_error クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfbaf1f0c88eaeb71bc4dfbbf2dca72c8d07251e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117440"
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
|[演算子 =](../cpp/com-error-operator-equal.md)|既存 **_com_error**を別のオブジェクト。|

### <a name="extractor-functions"></a>抽出関数

|||
|-|-|
|[エラー](../cpp/com-error-error.md)|コンス トラクターに渡された HRESULT を取得します。|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。|
|[WCode](../cpp/com-error-wcode.md)|カプセル化された HRESULT にマップされた 16 ビット エラー コードを取得します。|

### <a name="ierrorinfo-functions"></a>IErrorInfo の関数

|||
|-|-|
|[説明](../cpp/com-error-description.md)|`IErrorInfo::GetDescription` 関数を呼び出します。|
|[HelpContext](../cpp/com-error-helpcontext.md)|`IErrorInfo::GetHelpContext` 関数を呼び出します。|
|[HelpFile](../cpp/com-error-helpfile.md)|`IErrorInfo::GetHelpFile` 関数を呼び出します。|
|[Source](../cpp/com-error-source.md)|`IErrorInfo::GetSource` 関数を呼び出します。|
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

## <a name="requirements"></a>要件

**ヘッダー:** \<comdef.h >

`Lib:` comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)

## <a name="see-also"></a>関連項目

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo インターフェイス](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)