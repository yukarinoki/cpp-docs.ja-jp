---
title: COleSafeArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
dev_langs:
- C++
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e21cecc00c9aab170c79247bced635783541be48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376878"
---
# <a name="colesafearray-class"></a>COleSafeArray クラス
任意の型および次元の配列を扱うクラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](#colesafearray)|`COleSafeArray` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleSafeArray::AccessData](#accessdata)|配列データへのポインターを取得します。|  
|[COleSafeArray::AllocData](#allocdata)|配列のメモリを割り当てます。|  
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|セーフ配列記述子のメモリを割り当てます。|  
|[COleSafeArray::Attach](#attach)|既存のすべての制御**バリアント**配列を`COleSafeArray`オブジェクト。|  
|[COleSafeArray::Clear](#clear)|基になるすべてのデータを解放**バリアント**です。|  
|[COleSafeArray::Copy](#copy)|既存の配列のコピーを作成します。|  
|[COleSafeArray::Create](#create)|セーフ配列を作成します。|  
|[COleSafeArray::CreateOneDim](#createonedim)|1 次元作成`COleSafeArray`オブジェクト。|  
|[COleSafeArray::Destroy](#destroy)|既存の配列を破棄します。|  
|[COleSafeArray::DestroyData](#destroydata)|セーフ配列内のデータを破棄します。|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|セーフ配列の記述子を破棄します。|  
|[COleSafeArray::Detach](#detach)|デタッチ、**バリアント**の配列を`COleSafeArray`オブジェクト (データは解放されません) をします。|  
|[COleSafeArray::GetByteArray](#getbytearray)|セーフ配列の内容をコピー、 [CByteArray](../../mfc/reference/cbytearray-class.md)です。|  
|[COleSafeArray::GetDim](#getdim)|配列内の次元数を返します。|  
|[Colesafearray::getelement](#getelement)|セーフ配列の 1 つの要素を取得します。|  
|[COleSafeArray::GetElemSize](#getelemsize)|セーフ配列の 1 つの要素のバイト単位のサイズを返します。|  
|[COleSafeArray::GetLBound](#getlbound)|セーフ配列の任意の次元の下限の境界を返します。|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|1 次元で要素の数を返します`COleSafeArray`オブジェクト。|  
|[COleSafeArray::GetUBound](#getubound)|セーフ配列の任意の次元の上限の境界を返します。|  
|[COleSafeArray::Lock](#lock)|配列のロック カウントをインクリメントし、配列の記述子に配列データへのポインターを配置します。|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|インデックス付きの要素へのポインターを返します。|  
|[COleSafeArray::PutElement](#putelement)|1 つの要素を配列に割り当てます。|  
|[COleSafeArray::Redim](#redim)|セーフ配列の最下位 (右端) の境界を変更します。|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|1 次元内の要素の数を変更`COleSafeArray`オブジェクト。|  
|[COleSafeArray::UnaccessData](#unaccessdata)|デクリメント ロックは、配列のカウントし、によって取得されたポインターを無効に`AccessData`です。|  
|[COleSafeArray::Unlock](#unlock)|ロック カウントをデクリメント、配列の解放またはサイズ変更できるようにします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|基になるアクセス**バリアント**の構造、`COleSafeArray`オブジェクト。|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|基になるアクセス**バリアント**の構造、`COleSafeArray`オブジェクト。|  
|[COleSafeArray::operator =](#operator_eq)|値をコピー、`COleSafeArray`オブジェクト ( **SAFEARRAY**、**バリアント**、 `COleVariant`、または`COleSafeArray`配列)。|  
|[COleSafeArray::operator = =](#operator_eq_eq)|2 つのバリアント型の配列を比較 ( **SAFEARRAY**、**バリアント**、 `COleVariant`、または`COleSafeArray`配列)。|  
|[COleSafeArray::operator &lt;&lt;](#operator_lt_lt)|内容を出力、`COleSafeArray`ダンプ コンテキスト オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `COleSafeArray` OLE から派生した**バリアント**構造体。 OLE **SAFEARRAY**メンバー関数は、を通じて利用`COleSafeArray`、および一連のバイトの 1 次元配列用に設計されたメンバー関数として。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="accessdata"></a>  COleSafeArray::AccessData  
 配列データへのポインターを取得します。  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppvData`  
 配列データへのポインターへのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="allocdata"></a>  COleSafeArray::AllocData  
 セーフ配列にメモリを割り当てます。  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>コメント  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
##  <a name="allocdescriptor"></a>  COleSafeArray::AllocDescriptor  
 セーフ配列の記述子のメモリを割り当てます。  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDims`  
 セーフ配列の次元数。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
##  <a name="attach"></a>  COleSafeArray::Attach  
 既存のデータの制御**バリアント**配列を`COleSafeArray`オブジェクト。  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 A**バリアント**オブジェクト。 *VarSrc*パラメーターが必要、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**VT_ARRAY**です。  
  
### <a name="remarks"></a>コメント  
 ソース**バリアント**の種類に設定されて`VT_EMPTY`です。 この関数は、存在する場合に、現在の配列のデータをクリアします。  
  
### <a name="example"></a>例  
  例を参照して[COleSafeArray::AccessData](#accessdata)です。  
  
##  <a name="clear"></a>  COleSafeArray::Clear  
 セーフ配列を消去します。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 関数では、セーフ配列を消去を設定して、`VARTYPE`するオブジェクトの`VT_EMPTY`します。 現在の内容が解放され、配列が解放されます。  
  
##  <a name="colesafearray"></a>  COleSafeArray::COleSafeArray  
 `COleSafeArray` オブジェクトを構築します。  
  
```  
COleSafeArray();

 
COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

 
COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);  
  
COleSafeArray(const COleSafeArray& saSrc);  
COleSafeArray(const VARIANT& varSrc);  
  COleSafeArray(LPCVARIANT pSrc);  
COleSafeArray(const COleVariant& varSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `saSrc`  
 既存の`COleSafeArray`オブジェクトまたは**SAFEARRAY**新しいにコピーされる`COleSafeArray`オブジェクト。  
  
 `vtSrc`  
 **VARTYPE**新しい`COleSafeArray`オブジェクト。  
  
 `psaSrc`  
 ポインター、 **SAFEARRAY**新しいにコピーされる`COleSafeArray`オブジェクト。  
  
 *varSrc*  
 既存の**バリアント**または`COleVariant`新しいにコピーされるオブジェクト`COleSafeArray`オブジェクト。  
  
 `pSrc`  
 ポインター、**バリアント**新しいにコピーされるオブジェクト`COleSafeArray`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 新規作成すべてこれらのコンス トラクターの`COleSafeArray`オブジェクト。 空のパラメーターがない場合は`COleSafeArray`オブジェクトが作成された ( `VT_EMPTY`)。 場合、`COleSafeArray`が別のコピー元の配列[VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)は暗黙的に呼ばれます (、 `COleSafeArray`、 `COleVariant`、または**バリアント**) では、 **VARTYPE**のソース配列が保持され、指定する必要はありません。 場合、`COleSafeArray`が別のコピー元の配列**VARTYPE**既知ではありません ( **SAFEARRAY**) では、 **VARTYPE**で指定する必要があります、`vtSrc`パラメーター。  
  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
##  <a name="copy"></a>  COleSafeArray::Copy  
 既存のセーフ配列のコピーを作成します。  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>パラメーター  
 *ppsa*  
 新しい配列の記述子を返す先の場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
##  <a name="create"></a>  COleSafeArray::Create  
 配列のデータを初期化します。  
  
```  
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    DWORD* rgElements);

 
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    SAFEARRAYBOUND* rgsabounds);
```  
  
### <a name="parameters"></a>パラメーター  
 `vtSrc`  
 配列の基本型 (つまり、 **VARTYPE**配列の各要素の)。 **VARTYPE**バリアント型のサブセットに制限されます。 どちらも、 **VT_ARRAY**も**VT_BYREF**フラグを設定することができます。 `VT_EMPTY` および**VT_** 配列の有効な基本型ではありません。 他のすべての種類は無効です。  
  
 `dwDims`  
 配列の次元の数。 これは、配列の作成後に[Redim](#redim)です。  
  
 *rgElements*  
 配列内の各ディメンションの要素の数の配列へのポインター。  
  
 *rgsabounds*  
 (各ディメンションの 1 つ) の境界のベクターへのポインター、配列を割り当てられません。  
  
### <a name="remarks"></a>コメント  
 この関数は、必要に応じて、現在の配列のデータがクリアされます。 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="createonedim"></a>  COleSafeArray::CreateOneDim  
 新しい 1 次元`COleSafeArray`オブジェクト。  
  
```  
void CreateOneDim(
    VARTYPE vtSrc,  
    DWORD dwElements,  
    const void* pvSrcData = NULL,  
    long nLBound = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `vtSrc`  
 配列の基本型 (つまり、 **VARTYPE**配列の各要素の)。  
  
 `dwElements`  
 配列内の要素の数。 これは、配列の作成後に[でも](#resizeonedim)です。  
  
 `pvSrcData`  
 配列にコピーするデータへのポインター。  
  
 *nLBound*  
 配列の下限値です。  
  
### <a name="remarks"></a>コメント  
 関数は、の場合は、指定されたデータをコピー、配列のデータの初期化ポインター`pvSrcData`は**NULL**です。  
  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="destroy"></a>  COleSafeArray::Destroy  
 既存の配列の記述子と配列内のすべてのデータを破棄します。  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
##  <a name="destroydata"></a>  COleSafeArray::DestroyData  
 セーフ配列内のすべてのデータを破棄します。  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
##  <a name="destroydescriptor"></a>  COleSafeArray::DestroyDescriptor  
 セーフ配列の記述子を破棄します。  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>コメント  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
##  <a name="detach"></a>  COleSafeArray::Detach  
 デタッチ、**バリアント**からデータを`COleSafeArray`オブジェクト。  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>戻り値  
 基になる**バリアント**値で、`COleSafeArray`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 関数を設定して、セーフ配列内のデータの関連付けを解除、 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)するオブジェクトの`VT_EMPTY`します。 Windows の関数を呼び出すことによって、配列を解放する、呼び出し元の責任である[VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835)です。  
  
 エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)です。  
  
### <a name="example"></a>例  
  例を参照して[COleSafeArray::PutElement](#putelement)です。  
  
##  <a name="getbytearray"></a>  COleSafeArray::GetByteArray  
 セーフ配列の内容をコピー、`CByteArray`です。  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `bytes`  
 参照、 [CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクト。  
  
##  <a name="getdim"></a>  COleSafeArray::GetDim  
 内のディメンションの数を返します、`COleSafeArray`オブジェクト。  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>戻り値  
 セーフ配列の次元数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="getelement"></a>  Colesafearray::getelement  
 セーフ配列の 1 つの要素を取得します。  
  
```  
void GetElement(
    long* rgIndices,  
    void* pvData);
```  
  
### <a name="parameters"></a>パラメーター  
 `rgIndices`  
 インデックスの配列へのポインター (配列の次元ごと)。  
  
 `pvData`  
 配列の要素を配置する場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数は、自動的に windows 関数を呼び出して`SafeArrayLock`と`SafeArrayUnlock`前に、と後、要素を取得します。 データ要素が文字列、オブジェクト、またはバリアント型の場合は、関数は、適切な方法で要素をコピーします。 パラメーター`pvData`要素を格納するための十分なバッファーの大規模なをポイントする必要があります。  
  
 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="getelemsize"></a>  COleSafeArray::GetElemSize  
 内の要素のサイズを取得、`COleSafeArray`オブジェクト。  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>戻り値  
 セーフ配列の要素のバイト単位のサイズ。  
  
##  <a name="getlbound"></a>  COleSafeArray::GetLBound  
 任意の次元の下限の境界を返します、`COleSafeArray`オブジェクト。  
  
```  
void GetLBound(
    DWORD dwDim,  
    long* pLBound);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDim`  
 下限値を取得する対象の配列の次元です。  
  
 *pLBound*  
 下限の境界を返す場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="getonedimsize"></a>  COleSafeArray::GetOneDimSize  
 1 次元で要素の数を返します`COleSafeArray`オブジェクト。  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>戻り値  
 1 次元のセーフ配列内の要素の数。  
  
### <a name="example"></a>例  
  例を参照して[COleSafeArray::CreateOneDim](#createonedim)です。  
  
##  <a name="getubound"></a>  COleSafeArray::GetUBound  
 セーフ配列の任意の次元の上限の境界を返します。  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDim`  
 上限の境界を取得する対象の配列の次元です。  
  
 *pUBound*  
 上限の境界を返す場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="lock"></a>  COleSafeArray::Lock  
 配列と場所、データへのポインター、配列を配列の記述子のロック カウントをインクリメントします。  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>コメント  
 スローされるエラーの場合、 [COleException](../../mfc/reference/coleexception-class.md)です。  
  
 配列の記述子に、ポインターの有効期限`Unlock`と呼びます。 呼び出す`Lock`; 入れ子にすることができますへの呼び出しの数が等しい`Unlock`が必要です。  
  
 ロック中に、配列を削除できません。  
  
##  <a name="operator_lpcvariant"></a>  COleSafeArray::operator LPCVARIANT  
 基になるにアクセスするには、このキャスト演算子を呼び出す**バリアント**この構造体`COleSafeArray`オブジェクト。  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="operator_lpvariant"></a>  COleSafeArray::operator LPVARIANT  
 基になるにアクセスするには、このキャスト演算子を呼び出す**バリアント**この構造体`COleSafeArray`オブジェクト。  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>コメント  
 値を変更することに注意してください、**バリアント**の値を変更する構造体がこの関数によって返されるポインターは、アクセス`COleSafeArray`オブジェクト。  
  
##  <a name="operator_eq"></a>  COleSafeArray::operator =  
 これらのオーバー ロードされた代入演算子は、これに元の値をコピー`COleSafeArray`オブジェクト。  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>コメント  
 各演算子の簡単な説明に従います。  
  
- **演算子 = = (** *saSrc* **)** 、既存のコピー`COleSafeArray`オブジェクトをこのオブジェクトにします。  
  
- **演算子 = = (** *varSrc * * *)**、既存のコピー**バリアント**または`COleVariant`このオブジェクトの配列。  
  
- **演算子 = = (** `pSrc` **)** コピー、**バリアント**によってアクセスされる配列オブジェクト`pSrc`このオブジェクトにします。  
  
##  <a name="operator_eq_eq"></a>  COleSafeArray::operator = =  
 この演算子は、2 つの配列を比較 ( **SAFEARRAY**、**バリアント**、 `COleVariant`、または`COleSafeArray`配列) し、それらが等しい。 それ以外の場合 0 の場合は 0 以外を返します。  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
CDumpContext & AFXAPI 演算子 << (CDumpContext & dc では、  
    COleSafeArray & saSrc) です。
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
void PtrOfIndex (時間の長い * 返す時、  
    void * * ppvData) です。
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
void PutElement (時間の長い * 返す時、  
    void * pvData) です。
```  
  
### Parameters  
 `rgIndices`  
 Pointer to an array of indexes for each dimension of the array.  
  
 `pvData`  
 Pointer to the data to assign to the array. **VT_DISPATCH**, **VT_UNKNOWN**, and `VT_BSTR` variant types are pointers and do not require another level of indirection.  
  
### Remarks  
 This function automatically calls the Windows functions [SafeArrayLock](https://msdn.microsoft.com/library/windows/desktop/ms221492.aspx) and [SafeArrayUnlock](https://msdn.microsoft.com/library/windows/desktop/ms221246.aspx) before and after assigning the element. If the data element is a string, object, or variant, the function copies it correctly, and if the existing element is a string, object, or variant, it is cleared correctly.  
  
 Note that you can have multiple locks on an array, so you can put elements into an array while the array is locked by other operations.  
  
 On error, the function throws a [CMemoryException](../../mfc/reference/cmemoryexception-class.md) or [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
 [!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]  
  
##  <a name="redim"></a>  COleSafeArray::Redim  
 Changes the least significant (rightmost) bound of a safe array.  
  
```  
redim ステートメント (SAFEARRAYBOUND * psaboundNew); を無効にします。
```  
  
### Parameters  
 *psaboundNew*  
 Pointer to a new safe array bound structure containing the new array bound. Only the least significant dimension of an array may be changed.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim  
 Changes the number of elements in a one-dimensional `COleSafeArray` object.  
  
```  
void でも (DWORD dwElements) です。
```  
  
### Parameters  
 `dwElements`  
 Number of elements in the one-dimensional safe array.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData  
 Decrements the lock count of an array and invalidates the pointer retrieved by `AccessData`.  
  
```  
void UnaccessData() です。
```  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="unlock"></a>  COleSafeArray::Unlock  
 Decrements the lock count of an array so it can be freed or resized.  
  
```  
void Unlock() です。
```  
  
### Remarks  
 This function is called after access to the data in an array is finished. On error, it throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
## See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)
