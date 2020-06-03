---
title: CSocketFile クラス
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 83810a05925e5c8302240b61d95c131fdd78b426
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318170"
---
# <a name="csocketfile-class"></a>CSocketFile クラス

Windows ソケットを使ったネットワーク間でのデータの送受信に使われる `CFile` オブジェクトです。

## <a name="syntax"></a>構文

```
class CSocketFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイル::Cソケットファイル](#csocketfile)|`CSocketFile` オブジェクトを構築します。|

## <a name="remarks"></a>解説

この目的のためにオブジェクト`CSocketFile`をオブジェクトに`CSocket`アタッチできます。 また、MFC シリアル化を使用してデータ`CSocketFile`の送受信を`CArchive`簡単にするために、オブジェクトをオブジェクトにアタッチすることもできます。

データをシリアル化 (送信) するには、データをアーカイブ`CSocketFile``CSocket`に挿入します。 データを逆シリアル化 (受信) するには、アーカイブから抽出します。 これにより、アーカイブは、オブジェクト`CSocketFile`からデータを読み取るために`CSocket`メンバー関数を呼び出します。

> [!TIP]
> ここで説明`CSocketFile`する方法で使用する以外に、基本クラスと同様`CFile`に、スタンドアロンのファイル オブジェクトとして使用できます。 また、アーカイブ`CSocketFile`ベースの MFC シリアル化関数でも使用できます。 すべての`CSocketFile`機能をサポートしていないため、`CFile`既定の MFC シリアル化関数の一部は`CSocketFile`と互換性がありません。 これは特にクラスに`CEditView`当てはまります。 を`CEditView`使用して`CArchive``CSocketFile``CEditView::SerializeRaw`オブジェクトにアタッチされたオブジェクトを通じてデータをシリアル化しようとしないでください。代`CEditView::Serialize`わりに使用します。 この`SerializeRaw`関数は、ファイル オブジェクトに、含まれていない関数`Seek`などが`CSocketFile`含まれる必要があります。

と`CSocket`を`CArchive``CSocketFile`使用すると、要求されたバイト数を待`CSocket::Receive`つループがループ`PumpMessages(FD_READ)`に入る状況が発生する場合があります。 これは、Windows ソケットでは、FD_READ通知ごとに 1 つの recv `CSocketFile` `CSocket`呼び出ししか許可しませんが、FD_READごとに複数の recv 呼び出しを許可するためです。 読み取るデータがないときにFD_READを取得すると、アプリケーションがハングします。 FD_READがもうない場合、アプリケーションはソケット経由で通信を停止します。

この問題は、次のように解決できます。 ソケット`OnReceive`クラスのメソッドでは、ソケットから`CAsyncSocket::IOCtl(FIONREAD, ...)`読み取る`Serialize`データが 1 つの TCP パケットのサイズ (ネットワーク メディアの最大伝送単位、通常は少なくとも 1096 バイト) を超えたときに、メッセージ クラスのメソッドを呼び出す前に呼び出します。 使用可能なデータのサイズが必要以上に小さい場合は、すべてのデータが受信されるのを待ってから、読み取り操作を開始してください。

次の例では、`m_dwExpected`ユーザーが受信する必要があるおよそのバイト数を示します。 コード内の他の場所で宣言することを前提としています。

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

詳細については、「 MFC の[Windows ソケット](../../mfc/windows-sockets-in-mfc.md)」 を参照[してください。](../../mfc/windows-sockets-using-sockets-with-archives.md) [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsock.h

## <a name="csocketfilecsocketfile"></a><a name="csocketfile"></a>ファイル::Cソケットファイル

`CSocketFile` オブジェクトを構築します。

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>パラメーター

*ソケット*<br/>
オブジェクトにアタッチする`CSocketFile`ソケット。

*互換性のあるファイルをアーカイブする*<br/>
ファイル オブジェクトが`CArchive`オブジェクトで使用されるかどうかを指定します。 オブジェクトをスタンドアロンオブジェクトと同じように使用する`CSocketFile`場合に限り、特定の`CFile`制限がある場合にのみ FALSE を渡します。 このフラグは、オブジェクト`CArchive`にアタッチされたオブジェクト`CSocketFile`が読み取り用のバッファをどのように管理するかを変更します。

### <a name="remarks"></a>解説

オブジェクトがスコープ外に出たり削除されたりすると、オブジェクトのデストラクターは自身とソケット オブジェクトの関連付けを解除します。

> [!NOTE]
> A`CSocketFile`は`CArchive`、オブジェクトを持たない (限定された) ファイルとして使用することもできます。 既定では、コンストラクター`CSocketFile`の*bArchive 互換性パラメーター*は TRUE です。 これは、ファイルオブジェクトがアーカイブで使用されることを指定します。 アーカイブを使用せずにファイル オブジェクトを使用するには *、bArchiveCompatible*パラメーターに FALSE を渡します。

「アーカイブ互換」モードでは、オブジェクトの`CSocketFile`パフォーマンスが向上し、「デッドロック」の危険性が軽減されます。 デッドロックは、送信ソケットと受信ソケットの両方が互いに待機している場合、または共通のリソースを待機しているときに発生します。 この状況は、オブジェクトが`CArchive`オブジェクトと同`CSocketFile`じように動作した場合に発生することがあります`CFile`。 では`CFile`、アーカイブは、要求されたバイト数よりも少ないバイト数を受け取ると、ファイルの終わりに達したと想定できます。

ただし`CSocketFile`、 では、データはメッセージ ベースです。バッファーには複数のメッセージを含めることができるため、要求されたバイト数より少ない数を受信しても、ファイルの終わりを意味しません。 アプリケーションは、`CFile`での場合のようにブロックせず、バッファーが空になるまで、バッファーからメッセージを読み取り続けることができます。 [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty)関数は、このような場合にアーカイブのバッファの状態を監視するのに便利です。

の使用方法の詳細については、「 Windows ソケット : アーカイブと Windows[ソケットでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md) [: アーカイブを使用したソケットの使用例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)」を参照してください。 `CSocketFile`

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)
