---
title: CStrBufT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 695c3bc4c5e03f2ff6c1865f456b1ef358e3dcf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361359"
---
# <a name="cstrbuft-class"></a>CStrBufT クラス
このクラスは、自動リソース クリーンアップ`GetBuffer`と`ReleaseBuffer`、既存の呼び出し`CStringT`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>パラメーター  
 *TCharType*  
 文字型、`CStrBufT`クラスです。 次のいずれかの値を指定します。  
  
- `char` ANSI 文字列)  
  
- `wchar_t` (する Unicode 文字の文字列)  
  
- **TCHAR** (用、ANSI と Unicode 文字の文字列)  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`PCXSTR`|定数文字列へのポインター。|  
|`PXSTR`|文字列へのポインター。|  
|`StringType`|このクラス テンプレートの特殊化で操作するのには、バッファーが文字列型です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|文字列バッファー オブジェクトのコンス トラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|関連付けられている文字列オブジェクトの文字バッファーの長さを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|取得、 **const**関連付けられている文字列オブジェクトの文字バッファーへのポインター。|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|関連付けられている文字列オブジェクトの文字バッファーへのポインターを取得します。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|自動的に解放時に文字列の長さを決定します。|  
|[CStrBufT::SET_LENGTH](#set_length)|GetBuffer 時に、文字列オブジェクトの長さを設定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスへの呼び出しを置き換えるため、ラッパー クラスとして使用[GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と[ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)、または[GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)と`ReleaseBuffer`です。  
  
 ヘルパー クラスとして設計された`CStrBufT`について心配することがなく、文字列オブジェクトの文字バッファーを使用する開発者にとって便利な方法を呼び出すときに、または`ReleaseBuffer`です。 これは、ラッパー オブジェクトが例外または複数の既存コード パス以外の場合は必然的にスコープ外に出るため可能文字列リソースを解放するには、そのデストラクターが原因で。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  
  
##  <a name="auto_length"></a>  CStrBufT::AUTO_LENGTH  
 自動的に解放時に文字列の長さを決定します。  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>コメント  
 自動的に解放時に文字列の長さを決定します。 文字列は、null で終了する必要があります。  
  
##  <a name="cstrbuft"></a>  CStrBufT::CStrBufT  
 バッファー オブジェクトを構築します。  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 バッファーに関連付けられている文字列オブジェクト。 通常、開発者がの定義済みの typedef を使用**CStrBuf** ( **TCHAR**バリアント型)、 **CStrBufA** (`char`バリエーション) と**CStrBufW** (`wchar_t`バリアント型)。  
  
 *nMinLength*  
 文字バッファーの最小長。  
  
 `dwFlags`  
 文字列の長さが自動的に決定されるかどうかを判断します。 次のいずれかの値を指定します。  
  
- **AUTO_LENGTH**文字列の長さが自動的に決定するときに[CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)と呼びます。 文字列は、null で終了する必要があります。 既定値です。  
  
- **SET_LENGTH**場合、文字列の長さが設定[CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と呼びます。  
  
### <a name="remarks"></a>コメント  
 関連付けられている文字列オブジェクトの文字列バッファーを作成します。 構築時に、 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)または[CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)と呼びます。  
  
 なお、コピー コンス トラクターは`private`します。  
  
##  <a name="operator_pcxstr"></a>  CStrBufT::operator PCXSTR  
 関連付けられている文字列オブジェクトを C スタイルの文字列として格納されている文字に直接アクセスします。  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列のデータを指すポインターです。  
  
### <a name="remarks"></a>コメント  
 この関数では、文字列オブジェクトの文字バッファーへのポインターを返します。 このポインターでは、文字列オブジェクトの内容を変更できません。  
  
##  <a name="operator_pxstr"></a>  CStrBufT::operator PXSTR  
 関連付けられている文字列オブジェクトを C スタイルの文字列として格納されている文字に直接アクセスします。  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列のデータを指すポインターです。  
  
### <a name="remarks"></a>コメント  
 この関数では、文字列オブジェクトの文字バッファーへのポインターを返します。 開発者は、このポインターを持つ文字列オブジェクトの内容を変更できます。  
  
##  <a name="pcxstr"></a>  CStrBufT::PCXSTR  
 定数文字列へのポインター。  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="pxstr"></a>  CStrBufT::PXSTR  
 文字列へのポインター。  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="set_length"></a>  CStrBufT::SET_LENGTH  
 文字列オブジェクトの長さを設定して`GetBuffer`時間。  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>コメント  
 GetBuffer 時に、文字列オブジェクトの長さを設定します。  
  
 かどうかを[CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と[CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)文字列バッファー オブジェクトを作成するときと呼ばれます。  
  
##  <a name="setlength"></a>  CStrBufT::SetLength  
 文字バッファーの長さを設定します。  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLength`  
 文字列オブジェクトの文字バッファーの新しい長さ。  
  
> [!NOTE]
>  コンス トラクターで指定された最小バッファー長未満にする必要があります`CStrBufT`です。  
  
### <a name="remarks"></a>コメント  
 バッファー オブジェクトによって表される文字列の長さを設定するには、この関数を呼び出します。  
  
##  <a name="stringtype"></a>  CStrBufT::StringType  
 このクラス テンプレートの特殊化で操作するのには、バッファーが文字列型です。  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>コメント  
 **TCharType**クラス テンプレートの特定に使用される文字型です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)


