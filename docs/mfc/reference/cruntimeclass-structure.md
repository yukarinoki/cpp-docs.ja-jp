---
title: CRuntimeClass 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365247dc41ea75e67f63b2bb76b5bfe0c14a7ead
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376292"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass 構造体
各クラスから派生した`CObject`に関連付けられている、`CRuntimeClass`実行時に、オブジェクトまたはその基本クラスについての情報を取得するときに使用できる構造。  
  
## <a name="syntax"></a>構文  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](#createobject)|実行時にオブジェクトを作成します。|  
|[で](#fromname)|実行時にわかりやすいクラス名を使用して、オブジェクトを作成します。|  
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|クラスが指定したクラスから派生したかどうかを判断します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|クラスの名前。|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|オブジェクトのサイズ (バイト単位)。|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|ポインター、`CRuntimeClass`基底クラスの構造体。|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|オブジェクトを動的に作成する関数へのポインター。|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|返します、 `CRuntimeClass` (ときに動的に使用可能なリンクを参照) のみを構成します。|  
|[CRuntimeClass::m_wSchema](#m_wschema)|クラスのスキーマの数。|  
  
## <a name="remarks"></a>コメント  
 `CRuntimeClass` 構造体は、そのため、基底クラスはありません。  
  
 実行時にオブジェクトのクラスを判断することは、オブジェクトのクラスに基づく特殊なコードを記述する必要がありますまたは特別な型チェック関数の引数が必要な場合に便利です。 ランタイム クラス情報は、C++ 言語によって直接サポートされていません。  
  
 `CRuntimeClass` ポインターなどの C++ オブジェクトの関連情報を提供、`CRuntimeClass`基底クラスと関連するクラスの ASCII クラス名。 この構造体を使用して、既知の名前を関連するクラスが特定のクラスから派生したかどうかを決定するオブジェクトの種類を指定するオブジェクトを動的に作成するために使用できるさまざまな機能も実装します。  
  
 使用する方法についての`CRuntimeClass`、記事を参照して[クラス情報にアクセスする](../../mfc/accessing-run-time-class-information.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CRuntimeClass`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="createobject"></a>  CRuntimeClass::CreateObject  
 実行時に動的に指定したクラスを作成するには、この関数を呼び出します。  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 作成するクラスの既知の名前。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたオブジェクトへのポインターまたは**NULL**クラス名が見つからないか、メモリ不足のオブジェクトを作成する場合。  
  
### <a name="remarks"></a>コメント  
 派生したクラス`CObject`実行時に指定したクラスのオブジェクトを作成することが、動的な作成をサポートできます。 ドキュメント、ビュー、およびフレームのクラス、動的な作成をサポートするなどです。 動的な作成の詳細については、 `CreateObject` 、メンバーを参照してください[CObject クラス](../../mfc/using-cobject.md)と[CObject クラス: 機能のレベルを指定する](../../mfc/specifying-levels-of-functionality.md)です。  
  
### <a name="example"></a>例  
  例を参照して[IsDerivedFrom](#isderivedfrom)です。  
  
##  <a name="fromname"></a>  で  
 取得するには、この関数を呼び出して、`CRuntimeClass`既知の名前に関連付けられている構造体。  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 派生したクラスの使い慣れた名前`CObject`です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CRuntimeClass`で渡されたとは、名前に対応するオブジェクト`lpszClassName`です。 この関数を返します**NULL**一致するクラス名が見つからなかった場合です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>  CRuntimeClass::IsDerivedFrom  
 かどうか、呼び出し元がから派生したクラスに指定されたクラスを判断するには、この関数を呼び出して、*側*パラメーター。  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 *側*  
 派生したクラスの使い慣れた名前`CObject`です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合クラス通話`IsDerivedFrom`ベースから派生したクラス`CRuntimeClass`構造体は、それ以外のパラメーターとして指定された**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 リレーションシップは、「ウォーキング」チェーン派生クラスのメンバーのクラスから最上位までによって決定されます。 この関数のみを返します**FALSE**基底クラスの一致が検出されない場合。  
  
> [!NOTE]
>  使用する、`CRuntimeClass`構造体を含める必要があります、 `IMPLEMENT_DYNAMIC`、 `IMPLEMENT_DYNCREATE`、または`IMPLEMENT_SERIAL`マクロでは、実行時のオブジェクトの情報を取得するクラスの実装です。  
  
 使用する方法についての`CRuntimeClass`、記事を参照して[CObject クラス: クラス情報にアクセスする](../../mfc/accessing-run-time-class-information.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>  CRuntimeClass::m_lpszClassName  
 ASCII クラス名を含む null で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 この名前を使用して、クラスのインスタンスを作成するために使用できます、`FromName`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照して[IsDerivedFrom](#isderivedfrom)です。  
  
##  <a name="m_nobjectsize"></a>  CRuntimeClass::m_nObjectSize  
 (バイト単位)、オブジェクトのサイズ。  
  
### <a name="remarks"></a>コメント  
 オブジェクトは、割り当てられたメモリを指すデータ メンバーが、そのメモリのサイズは含まれません。  
  
### <a name="example"></a>例  
  例を参照して[IsDerivedFrom](#isderivedfrom)です。  
  
##  <a name="m_pbaseclass"></a>  CRuntimeClass::m_pBaseClass  
 このデータ メンバーがへのポインターを含む、アプリケーションは、MFC と静的にリンクすることが場合、`CRuntimeClass`基底クラスの構造体。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、MFC ライブラリに動的にリンクすることが場合、は、次を参照してください。 [m_pfnGetBaseClass](#m_pfngetbaseclass)です。  
  
### <a name="example"></a>例  
  例を参照して[IsDerivedFrom](#isderivedfrom)です。  
  
##  <a name="m_pfncreateobject"></a>  CRuntimeClass::m_pfnCreateObject  
 クラスのオブジェクトを作成する既定のコンス トラクターへの関数ポインター。  
  
### <a name="remarks"></a>コメント  
 このポインターが有効なは、クラスは、動的な作成をサポートしている場合のみ関数を返しますそれ以外の場合、 **NULL**です。  
  
##  <a name="m_pfngetbaseclass"></a>  CRuntimeClass::m_pfnGetBaseClass  
 アプリケーションは、共有 DLL としての MFC ライブラリを使用する場合は、このデータへのポインターを返す関数、`CRuntimeClass`基底クラスの構造体。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、MFC ライブラリに静的にリンクすることが場合、は、次を参照してください。 [m_pBaseClass](#m_pbaseclass)です。  
  
### <a name="example"></a>例  
  例を参照して[IsDerivedFrom](#isderivedfrom)です。  
  
##  <a name="m_wschema"></a>  CRuntimeClass::m_wSchema  
 スキーマの数 (シリアル化できないクラスの場合は-1)。  
  
### <a name="remarks"></a>コメント  
 スキーマの番号の詳細については、次を参照してください。、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロです。  
  
### <a name="example"></a>例  
  例を参照して[IsDerivedFrom](#isderivedfrom)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)   
 [使うため](../../mfc/reference/cobject-class.md#iskindof)   
 [RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)   
 [新規クラス](run-time-object-model-services.md#implement_dynamic)   
 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)   
 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)



