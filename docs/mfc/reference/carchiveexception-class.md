---
title: CArchiveException クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2763335a9165c1667160864a40200dcfd44b7f34
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953101"
---
# <a name="carchiveexception-class"></a>CArchiveException クラス
シリアル化の例外条件を表します  
  
## <a name="syntax"></a>構文  
  
```  
class CArchiveException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CArchiveException::CArchiveException](#carchiveexception)|`CArchiveException` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CArchiveException::m_cause](#m_cause)|例外の原因を示します。|  
|[CArchiveException::m_strFileName](#m_strfilename)|この例外条件については、ファイルの名前を指定します。|  
  
## <a name="remarks"></a>Remarks  
 `CArchiveException`クラスには、例外の原因を示すパブリック データ メンバーが含まれています。  
  
 `CArchiveException` オブジェクトが構築され、内でスロー [CArchive](../../mfc/reference/carchive-class.md)メンバー関数。 これらのオブジェクトのスコープ内にアクセスすることができます、**キャッチ**式。 原因のコードは、オペレーティング システムの依存しません。 例外の処理の詳細については、次を参照してください。[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afx.h  
  
##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException  
 構築、`CArchiveException`の値を格納するオブジェクト*原因*オブジェクトにします。  
  
```  
CArchiveException(
    int cause = CArchiveException::none,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *cause*  
 例外の理由を示す列挙型の変数です。 列挙子の一覧は、次を参照してください。、[は](#m_cause)データ メンバーです。  
  
 *lpszArchiveName*  
 名前を含む文字列を指す、`CArchive`例外の原因とします。  
  
### <a name="remarks"></a>Remarks  
 作成することができます、`CArchiveException`グローバル関数のヒープ上のオブジェクトし自分でスローさせたり[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)を処理します。  
  
 このコンス トラクターを直接使用しないでください。代わりに、グローバル関数を呼び出して`AfxThrowArchiveException`です。  
  
##  <a name="m_cause"></a>  CArchiveException::m_cause  
 例外の原因を指定します。  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Remarks  
 このデータ メンバーは型のパブリック変数**int**です。その値は、`CArchiveException`列挙型。 列挙子とその意味は次のとおりです。  
  
- **CArchiveException::none**エラーが発生していません。  
  
- **CArchiveException::genericException**エラーを特定できません。  
  
- **CArchiveException::readOnly**読み込みのために開かれたアーカイブに書き込もうとしました。  
  
- **CArchiveException::endOfFile**に達しましたファイルの終わりオブジェクトの読み取り中にします。  
  
- **CArchiveException::writeOnly**を格納するために開かれたアーカイブから読み取ろうとしました。  
  
- **CArchiveException::badIndex**ファイル形式が無効です。  
  
- **CArchiveException::badClass**誤った型のオブジェクトに、オブジェクトを読み取るしようとしています。  
  
- **CArchiveException::badSchema**クラスの別のバージョンを持つオブジェクトを読み込もうとしました。  
  
    > [!NOTE]
    >  これらの `CArchiveException` 原因列挙子は、`CFileException` 原因列挙子とは異なります。  
  
    > [!NOTE]
    > **CArchiveException::generic**は推奨されなくなりました。 使用して**代わり**代わりにします。 場合**ジェネリック**アプリケーションで使用され、ビルドは/clr ではエラーが発生する構文を解読する簡単ではありません。  
  
##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName  
 この例外条件については、ファイルの名前を指定します。  
  
```  
CString m_strFileName;  
```  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CArchive クラス](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)   
 [例外処理](../../mfc/reference/exception-processing.md)

