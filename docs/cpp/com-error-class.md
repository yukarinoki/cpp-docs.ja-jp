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
ms.openlocfilehash: 0d59782b62ddfb51601505be6d12f01ce14cd4f1
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026635"
---
# <a name="comerror-class"></a>_com_error クラス
**Microsoft 固有の仕様**  
  
 `_com_error` オブジェクトは、タイプ ライブラリから生成されるヘッダー ファイル内のエラー処理ラッパー関数によって、またはいずれかの COM サポート クラスによって検出される例外条件を表します。 `_com_error` HRESULT エラー コードおよび関連クラスがカプセル化`IErrorInfo Interface`オブジェクト。  
  
### <a name="construction"></a>構築  
  
|||  
|-|-|  
|[_com_error](../cpp/com-error-com-error.md)|`_com_error` オブジェクトを構築します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../cpp/com-error-operator-equal.md)|既存の `_com_error` オブジェクトを別のオブジェクトに割り当てます。|  
  
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
|[エラー メッセージ](../cpp/com-error-errormessage.md)|`_com_error` オブジェクトに格納された HRESULT の文字列メッセージを取得します。|  
  
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
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo インターフェイス](http://msdn.microsoft.com/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)