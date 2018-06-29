---
title: CSimpleException クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be5d27adabe8b271e2f8f3ed338e63e18d2432fc
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078237"
---
# <a name="csimpleexception-class"></a>CSimpleException クラス
このクラスは、リソース クリティカルな MFC 例外の基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|発生したエラーに関するテキストを提供します。|  
  
## <a name="remarks"></a>Remarks  
 `CSimpleException` リソース クリティカルな MFC 例外の基底クラスと所有権とエラー メッセージの初期化を処理します。 次のクラスを使用して`CSimpleException`その基本クラスとして。  
  
|||  
|-|-|  
|[CMemoryException クラス](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|  
|[CNotSupportedException クラス](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作に対する要求|  
|[CResourceException クラス](../../mfc/reference/cresourceexception-class.md)|Windows リソース見つからないか、または不可能|  
|[CUserException クラス](../../mfc/reference/cuserexception-class.md)|リソースを示す例外が見つかりませんでした。|  
|[CInvalidArgException クラス](../../mfc/reference/cinvalidargexception-class.md)|無効な引数を示す例外|  
  
 `CSimpleException`抽象基本クラスでは、宣言することはできません、`CSimpleException`オブジェクトに直接できます。 代わりに、前の表に示すなどの派生オブジェクトを宣言する必要があります。 派生クラスを宣言する場合は、モデルとして前のクラスを使用します。  
  
 詳細については、次を参照してください。、 [CException クラス](../../mfc/reference/cexception-class.md)トピックおよび[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afx.h  
  
##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException  
 コンストラクターです。  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAutoDelete*  
 指定**TRUE**場合のメモリを`CSimpleException`オブジェクトは、ヒープに割り当てられました。 これにより、`CSimpleException`ときに削除されるオブジェクト、`Delete`例外を削除するメンバー関数が呼び出されます。 指定**FALSE**場合、`CSimpleException`オブジェクトがスタック上またはグローバル オブジェクトです。 ここで、`CSimpleException`されない時に削除、`Delete`メンバー関数が呼び出されます。  
  
### <a name="remarks"></a>Remarks  
 このコンス トラクターを直接呼び出す必要は通常ありません。 例外をスローした関数がのインスタンスを作成する必要があります、 `CException`-クラスを派生し、そのコンス トラクター、または呼び出しが、MFC のいずれかを使用スローすることは、関数など[AfxThrowFileException](exception-processing.md#afxthrowfileexception)、定義済みの型をスローします。  
  
##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage  
 発生したエラーに関するテキストを提供するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszError*  
 エラー メッセージを受信するバッファーへのポインター。  
  
 *nMaxError*  
 バッファーに保持できる文字の最大数、 **NULL**ターミネータです。  
  
 *pnHelpContext*  
 アドレス、 **UINT**ヘルプ コンテキスト ID を受信します。 場合**NULL**ID は返されません。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 (ゼロ) の場合、エラー メッセージ テキストは使用できます。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [例外処理](../../mfc/exception-handling-in-mfc.md)



