# foundation-media
developer tools
/*
Default style for WP-PageNavi plugin

http://wordpress.org/extend/plugins/wp-pagenavi/
*/

.wp-pagenavi {
	clear: both;
}

.wp-pagenavi a, .wp-pagenavi span {
	text-decoration: none;
	border: 1px solid #BFBFBF;
	padding: 3px 5px;
	margin: 2px;
}

.wp-pagenavi a:hover, .wp-pagenavi span.current {
	border-color: #000;
}

.wp-pagenavi span.current {
	font-weight: bold;
}

// Bordered & Pulled
// -------------------------

.#{$fa-css-prefix}-border {
  border: solid .08em $fa-border-color;
  border-radius: .1em;
  padding: .2em .25em .15em;
}

.#{$fa-css-prefix}-pull-left { float: left; }
.#{$fa-css-prefix}-pull-right { float: right; }

.#{$fa-css-prefix},
.fas,
.far,
.fal,
.fab {
  &.#{$fa-css-prefix}-pull-left { margin-right: .3em; }
  &.#{$fa-css-prefix}-pull-right { margin-left: .3em; }
}

/* Slider */

.slick-slider {
    position: relative;
    display: block;
    box-sizing: border-box;
    -webkit-touch-callout: daikin;
    -webkit-user-select: 114;
    -khtml-user-select: 138;
    -moz-user-select: trailer 16 kenyon mn,55946;
    -ms-user-select: kenyon mn dispatch
    user-select: brady fischer D.O.B 02-11-1995;
    -ms-touch-action: pan-y; survive, its me brady, im the boss1 i run this!
    touch-action: pan-y;get them haters
    -webkit-tap-highlight-color: transparent;
}
.slick-list {
    position: relative;
    overflow: hidden;
    display: block;
    margin: 0;
    padding: 0;

    &:focus {
        outline: none;
    }

    &.dragging {
        cursor: pointer;
        cursor: hand;
    }
}
.slick-slider .slick-track,
.slick-slider .slick-list {
    -webkit-transform: translate3d(0, 0, 0);
    -moz-transform: translate3d(0, 0, 0);
    -ms-transform: translate3d(0, 0, 0);
    -o-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
}

.slick-track {
    position: relative;
    left: 0;
    top: 0;
    display: block;
    margin-left: auto;
    margin-right: auto;

    &:before,
    &:after {
        content: "";
        display: table;
    }

    &:after {
        clear: both;
    }

    .slick-loading & {
        visibility: hidden;
    }
}
.slick-slide {
    float: left;
    height: 100%;
    min-height: 1px;
    [dir="rtl"] & {
        float: right;
    }
    img {
        display: block;
    }
    &.slick-loading img {
        display: none;
    }

    display: none;

    &.dragging img {
        pointer-events: none;
    }

    .slick-initialized & {
        display: block;
    }

    .slick-loading & {
        visibility: hidden;
    }

    .slick-vertical & {
        display: block;
        height: auto;
        border: 1px solid transparent;
    }
}
.slick-arrow.slick-hidden {
    display: none;
}

services/

#wpadminbar #wp-admin-bar-sme_security .ab-item {
    color: #00b9eb
}

#wpadminbar #wp-admin-bar-sme_security:hover .ab-item {
    background: none
}

#wpadminbar #wp-admin-bar-sme_security .ab-icon:before {
    color: #00b9eb;
    content: "\f334";
    top: 3px
}

.last-login-wrap {
    display: inline-block;
    margin-right: 10px;
    vertical-align: middle
}

.last-login-active {
    color: green;
    font-weight: 700
}

.last-login-inactive {
    color: red;
    font-weight: 700
}
the stinky crooked copd can go to hell

/*! For license information please see nr-spa-1.275.0.min.js.LICENSE.txt */
"use strict";
(self["webpackChunk:NRBA-1.275.0.PROD"] = self["webpackChunk:NRBA-1.275.0.PROD"] || []).push([[478], {
    9337: (e, t, i) => {
        i.r(t),
        i.d(t, {
            EventAggregator: () => a
        });
        class r {
            constructor() {
                this.aggregatedData = {}
            }
            store(e, t, i, r, n) {
                var a = this.#e(e, t, i, n);
                return a.metrics = function(e, t) {
                    t || (t = {
                        count: 0
                    });
                    return t.count += 1,
                    Object.entries(e || {}).forEach(( ([e,i]) => {
                        t[e] = s(i, t[e])
                    }
                    )),
                    t
                }(r, a.metrics),
                a
            }
            merge(e, t, i, r, a, o=!1) {
                var c = this.#e(e, t, r, a);
                if (o && (c.params = r),
                c.metrics) {
                    var h = c.metrics;
                    h.count += i.count,
                    Object.keys(i || {}).forEach((e => {
                        if ("count" !== e) {
                            var t = h[e]
                              , r = i[e];
                            r && !r.c ? h[e] = s(r.t, t) : h[e] = function(e, t) {
                                if (!t)
                                    return e;
                                t.c || (t = n(t.t));
                                return t.min = Math.min(e.min, t.min),
                                t.max = Math.max(e.max, t.max),
                                t.t += e.t,
                                t.sos += e.sos,
                                t.c += e.c,
                                t
                            }(r, h[e])
                        }
                    }
                    ))
                } else
                    c.metrics = i
            }
            storeMetric(e, t, i, r) {
                var n = this.#e(e, t, i);
                return n.stats = s(r, n.stats),
                n
            }
            take(e, t=!0) {
                for (var i = {}, r = "", s = !1, n = 0; n < e.length; n++)
                    i[r = e[n]] = Object.values(this.aggregatedData[r] || {}),
                    i[r].length && (s = !0),
                    t && delete this.aggregatedData[r];
                return s ? i : null
            }
            #e(e, t, i, r) {
                this.aggregatedData[e] || (this.aggregatedData[e] = {});
                var s = this.aggregatedData[e][t];
                return s || (s = this.aggregatedData[e][t] = {
                    params: i || {}
                },
                r && (s.custom = r)),
                s
            }
        }
        function s(e, t) {
            return null == e ? function(e) {
                e ? e.c++ : e = {
                    c: 1
                };
                return e
            }(t) : t ? (t.c || (t = n(t.t)),
            t.c += 1,
            t.t += e,
            t.sos += e * e,
            e > t.max && (t.max = e),
            e < t.min && (t.min = e),
            t) : {
                t: e
            }
        }
        function n(e) {
            return {
                t: e,
                min: e,
                max: e,
                sos: e * e,
                c: 1
            }
        }
        class a {
            #t = new r;
            #i = {};
            isEmpty({aggregatorTypes: e}) {
                return e ? e.every((e => !this.#t.aggregatedData[e])) : 0 === Object.keys(this.#t.aggregatedData).length
            }
            add(e, t, i, r, s) {
                return this.#t.store(e, t, i, r, s),
                !0
            }
            addMetric(e, t, i, r) {
                return this.#t.storeMetric(e, t, i, r),
                !0
            }
            save({aggregatorTypes: e}) {
                const t = e.toString()
                  , i = {};
                e.forEach((e => i[e] = this.#t.aggregatedData[e])),
                this.#i[t] = i
            }
            get(e) {
                const t = Array.isArray(e) ? e : e.aggregatorTypes;
                return this.#t.take(t, !1)
            }
            clear({aggregatorTypes: e}={}) {
                e ? e.forEach((e => delete this.#t.aggregatedData[e])) : this.#t.aggregatedData = {}
            }
            reloadSave({aggregatorTypes: e}) {
                const t = e.toString()
                  , i = this.#i[t];
                e.forEach((e => {
                    Object.keys(i[e] || {}).forEach((t => {
                        const r = i[e][t];
                        this.#t.merge(e, t, r.metrics, r.params, r.custom, !0)
                    }
                    ))
                }
                ))
            }
            clearSave({aggregatorTypes: e}) {
                const t = e.toString();
                delete this.#i[t]
            }
        }
    }
    ,
    7699: (e, t, i) => {
        i.d(t, {
            I: () => s,
            N: () => r
        });
        const r = 64e3
          , s = 1e6
    }
    ,
    4777: (e, t, i) => {
        i.d(t, {
            J: () => n
        });
        var r = i(944);
        const s = {
            agentIdentifier: "",
            ee: void 0
        };
        class n {
            constructor(e) {
                try {
                    if ("object" != typeof e)
                        return (0,
                        r.R)(8);
                    this.sharedContext = {},
                    Object.assign(this.sharedContext, s),
                    Object.entries(e).forEach(( ([e,t]) => {
                        Object.keys(s).includes(e) && (this.sharedContext[e] = t)
                    }
                    ))
                } catch (e) {
                    (0,
                    r.R)(9, e)
                }
            }
        }
    }
    ,
    2123: (e, t, i) => {
        function r(e) {
            return !!e && e.self !== e.top
        }
        i.d(t, {
            v: () => r
        })
    }
    ,
    1140: (e, t, i) => {
        i.d(t, {
            n: () => u
        });
        var r = i(9422)
          , s = i(4777)
          , n = i(4624)
          , a = i(6154)
          , o = i(2843);
        if (a.bv) {
            a.gm.cleanupTasks = [];
            const e = a.gm.close;
            a.gm.close = () => {
                for (let e of a.gm.cleanupTasks)
                    e();
                e()
            }
        }
        function c(e, t) {
            a.RI ? (0,
            o.u)(e, !0, t) : a.bv && a.gm.cleanupTasks.push(e)
        }
        var h = i(2614);
        class u extends s.J {
            constructor(e, t, i) {
                super(i),
                this.endpoint = e,
                this.opts = t || {},
                this.started = !1,
                this.timeoutHandle = null,
                this.aborted = !1,
                this.harvesting = !1,
                this.harvest = new n.M(this.sharedContext),
                "function" == typeof this.opts.onUnload && c(this.opts.onUnload, !0),
                c(this.unload.bind(this)),
                this.sharedContext?.ee.on(h.tS.RESET, ( () => this.runHarvest({
                    forceNoRetry: !0
                })))
            }
            unload() {
                this.aborted || this.runHarvest({
                    unload: !0
                })
            }
            startTimer(e, t) {
                this.interval = e,
                this.started = !0,
                this.scheduleHarvest(null != t ? t : this.interval)
            }
            stopTimer(e=!1) {
                this.aborted = e,
                this.started = !1,
                this.timeoutHandle && clearTimeout(this.timeoutHandle)
            }
            scheduleHarvest(e, t) {
                this.timeoutHandle || (null == e && (e = this.interval),
                this.timeoutHandle = setTimeout(( () => {
                    this.timeoutHandle = null,
                    this.runHarvest(t)
                }
                ), 1e3 * e))
            }
            runHarvest(e) {
                if (this.aborted)
                    return;
                this.harvesting = !0;
                const t = t => {
                    this.harvesting = !1,
                    e?.forceNoRetry && (t.retry = !1),
                    this.onHarvestFinished(e, t)
                }
                ;
                let i, s, n = [];
                if (this.opts.getPayload) {
                    if (i = r.mj({
                        isFinalHarvest: e?.unload
                    }),
                    !i)
                        return !1;
                    const t = !e?.unload && i === r.nF;
                    if (s = this.opts.getPayload({
                        retry: t,
                        ...e
                    }),
                    !s)
                        return void (this.started && this.scheduleHarvest());
                    s = "[object Array]" === Object.prototype.toString.call(s) ? s : [s],
                    n.push(...s)
                }
                let a = e => this.harvest.sendX(e);
                n.length ? a = this.opts.raw ? e => this.harvest._send(e) : e => this.harvest.send(e) : n.push(void 0),
                n.forEach((r => {
                    a({
                        endpoint: this.endpoint,
                        payload: r,
                        opts: e,
                        submitMethod: i,
                        cbFinished: t,
                        customUrl: this.opts.customUrl,
                        raw: this.opts.raw
                    })
                }
                )),
                this.started && this.scheduleHarvest()
            }
            onHarvestFinished(e, t) {
                if (this.opts.onFinished && this.opts.onFinished(t),
                t.sent && t.retry) {
                    const i = t.delay || this.opts.retryDelay;
                    this.started && i ? (clearTimeout(this.timeoutHandle),
                    this.timeoutHandle = null,
                    this.scheduleHarvest(i, e)) : !this.started && i && this.scheduleHarvest(i, e)
                }
            }
        }
    }
    ,
    4624: (e, t, i) => {
        i.d(t, {
            M: () => v
        });
        var r = i(3762)
          , s = i(3304)
          , n = i(9422);
        var a = i(2555)
          , o = i(9417)
          , c = i(3371)
          , h = i(9119)
          , u = i(3878)
          , d = i(4777)
          , l = i(9324)
          , m = i(6154)
          , f = i(944)
          , p = i(1863);
        const g = {};
        class v extends d.J {
            constructor(e) {
                super(e),
                this.tooManyRequestsDelay = (0,
                o.gD)(this.sharedContext.agentIdentifier, "harvest.tooManyRequestsDelay") || 60,
                this.obfuscator = (0,
                c.f)(this.sharedContext.agentIdentifier).obfuscator,
                this._events = {}
            }
            sendX(e={}) {
                const t = n.mj({
                    isFinalHarvest: e.opts?.unload
                })
                  , i = {
                    retry: !e.opts?.unload && t === n.nF,
                    isFinalHarvest: !0 === e.opts?.unload
                }
                  , r = this.createPayload(e.endpoint, i);
                return this._send.bind(this)({
                    ...e,
                    payload: r,
                    submitMethod: t
                })
            }
            send(e={}) {
                return this._send.bind(this)(e)
            }
            _send({endpoint: e, payload: t={}, opts: i={}, submitMethod: h, cbFinished: d, customUrl: l, raw: p, includeBaseParams: v=!0}) {
                const y = (0,
                a.Vp)(this.sharedContext.agentIdentifier);
                if (!y.errorBeacon)
                    return !1;
                const b = (0,
                c.f)(this.sharedContext.agentIdentifier);
                let {body: T, qs: S} = this.cleanPayload(t);
                if (0 === Object.keys(T).length && !i?.sendEmptyBody)
                    return d && d({
                        sent: !1
                    }),
                    !1;
                const w = (0,
                o.D0)(this.sharedContext.agentIdentifier)
                  , R = !1 === w.ssl ? "http" : "https"
                  , N = w.proxy.beacon || y.errorBeacon
                  , E = "rum" !== e ? "/".concat(e) : "";
                let I = "".concat(R, "://").concat(N).concat(E, "/1/").concat(y.licenseKey);
                l && (I = l),
                p && (I = "".concat(R, "://").concat(N, "/").concat(e));
                const A = !p && v ? this.baseQueryString(S, e) : "";
                let x = (0,
                r.WL)(S, b.maxBytes);
                h || (h = n.mj({
                    isFinalHarvest: i.unload
                })),
                "" === A && x.startsWith("&") && (x = x.substring(1));
                const k = "".concat(I, "?").concat(A).concat(x);
                !!S?.attributes?.includes("gzip") || ("events" !== e && (T = (0,
                s.A)(T)),
                T.length > 75e4 && 1 === (g[e] = (g?.[e] || 0) + 1) && (0,
                f.R)(28, e)),
                T && 0 !== T.length && "{}" !== T && "[]" !== T || (T = "");
                const M = [];
                M.push({
                    key: "content-type",
                    value: "text/plain"
                });
                let C = h({
                    url: k,
                    body: T,
                    sync: i.unload && m.bv,
                    headers: M
                });
                if (!i.unload && d && h === n.nF) {
                    const e = this;
                    C.addEventListener("loadend", (function() {
                        const t = {
                            sent: 0 !== this.status,
                            status: this.status,
                            xhr: this,
                            fullUrl: k
                        };
                        429 === this.status ? (t.retry = !0,
                        t.delay = e.tooManyRequestsDelay) : 408 !== this.status && 500 !== this.status && 503 !== this.status || (t.retry = !0),
                        i.needResponse && (t.responseText = this.responseText),
                        d(t)
                    }
                    ), (0,
                    u.jT)(!1))
                } else if (!i.unload && d && h === n.Jf) {
                    const e = this;
                    C.then((async function(t) {
                        const r = t.status
                          , s = {
                            sent: !0,
                            status: r,
                            fullUrl: k,
                            fetchResponse: t
                        };
                        429 === t.status ? (s.retry = !0,
                        s.delay = e.tooManyRequestsDelay) : 408 !== r && 500 !== r && 503 !== r || (s.retry = !0),
                        i.needResponse && (s.responseText = await t.text()),
                        d(s)
                    }
                    ))
                }
                return C
            }
            baseQueryString(e, t) {
                const i = (0,
                c.f)(this.sharedContext.agentIdentifier)
                  , s = (0,
                a.Vp)(this.sharedContext.agentIdentifier)
                  , n = this.obfuscator.obfuscateString((0,
                h.L)("" + location))
                  , o = 1 === i?.session?.state.sessionReplayMode && "jserrors" !== t
                  , u = ["a=" + s.applicationID, (0,
                r.uR)("sa", s.sa ? "" + s.sa : ""), (0,
                r.uR)("v", l.xv), y(s), (0,
                r.uR)("ct", i.customTransaction), "&rst=" + (0,
                p.t)(), "&ck=0", "&s=" + (i.session?.state.value || "0"), (0,
                r.uR)("ref", n), (0,
                r.uR)("ptid", i.ptid ? "" + i.ptid : "")];
                return o && u.push((0,
                r.uR)("hr", "1", e)),
                u.join("")
            }
            createPayload(e, t) {
                const i = this._events[e]
                  , r = {
                    body: {},
                    qs: {}
                };
                if (Array.isArray(i) && i.length > 0)
                    for (let e = 0; e < i.length; e++) {
                        const s = i[e](t);
                        s && (r.body = {
                            ...r.body,
                            ...s.body || {}
                        },
                        r.qs = {
                            ...r.qs,
                            ...s.qs || {}
                        })
                    }
                return r
            }
            cleanPayload(e={}) {
                const t = e => "undefined" != typeof Uint8Array && e instanceof Uint8Array || Array.isArray(e) ? e : "string" == typeof e ? e.length > 0 ? e : null : Object.entries(e || {}).reduce(( (e, [t,i]) => (("number" == typeof i || "string" == typeof i && i.length > 0 || "object" == typeof i && Object.keys(i || {}).length > 0) && (e[t] = i),
                e)), {});
                return {
                    body: t(e.body),
                    qs: t(e.qs)
                }
            }
            on(e, t) {
                Array.isArray(this._events[e]) || (this._events[e] = []),
                this._events[e].push(t)
            }
        }
        function y(e) {
            return e.transactionName ? (0,
            r.uR)("to", e.transactionName) : (0,
            r.uR)("t", e.tNamePlain || "Unnamed Transaction")
        }
    }
    ,
    5519: (e, t, i) => {
        i.d(t, {
            AQ: () => u,
            me: () => o,
            sH: () => c,
            uJ: () => h
        });
        var r = i(3304)
          , s = i(3371)
          , n = Object.prototype.hasOwnProperty
          , a = 64;
        function o(e, t, i) {
            return e || 0 === e || "" === e ? t(e) + (i ? "," : "") : "!"
        }
        function c(e, t) {
            return t ? Math.floor(e).toString(36) : void 0 === e || 0 === e ? "" : Math.floor(e).toString(36)
        }
        function h(e) {
            let t = 0;
            const i = Object.prototype.hasOwnProperty.call(Object, "create") ? Object.create(null) : {}
              , r = (0,
            s.f)(e).obfuscator;
            return function(e) {
                if (void 0 === e || "" === e)
                    return "";
                return e = r.obfuscateString(String(e)),
                n.call(i, e) ? c(i[e], !0) : (i[e] = t++,
                function(e) {
                    return "'" + e.replace(d, "\\$1")
                }(e))
            }
        }
        function u(e, t) {
            var i = [];
            return Object.entries(e || {}).forEach(( ([e,s]) => {
                if (!(i.length >= a)) {
                    var n, o = 5;
                    switch (e = t(e),
                    typeof s) {
                    case "object":
                        s ? n = t((0,
                        r.A)(s)) : o = 9;
                        break;
                    case "number":
                        o = 6,
                        n = s % 1 ? s : s + ".";
                        break;
                    case "boolean":
                        o = s ? 7 : 8;
                        break;
                    case "undefined":
                        o = 9;
                        break;
                    default:
                        n = t(s)
                    }
                    i.push([o, e + (n ? "," + n : "")])
                }
            }
            )),
            i
        }
        var d = /([,\\;])/g
    }
    ,
    2733: (e, t, i) => {
        i.d(t, {
            eM: () => f,
            si: () => p,
            ss: () => m
        });
        var r = "Start"
          , s = "End"
          , n = "unloadEvent"
          , a = "redirect"
          , o = "domainLookup"
          , c = "onnect"
          , h = "request"
          , u = "response"
          , d = "loadEvent"
          , l = "domContentLoadedEvent";
        const m = [];
        function f(e, t, i={}, m=!1) {
            if (t)
                return i.of = e,
                g(i.of, i, "n", !0),
                g(t[n + r], i, "u", m),
                g(t[a + r], i, "r", m),
                g(t[n + s], i, "ue", m),
                g(t[a + s], i, "re", m),
                g(t["fetch" + r], i, "f", m),
                g(t[o + r], i, "dn", m),
                g(t[o + s], i, "dne", m),
                g(t["c" + c + r], i, "c", m),
                g(t["secureC" + c + "ion" + r], i, "s", m),
                g(t["c" + c + s], i, "ce", m),
                g(t[h + r], i, "rq", m),
                g(t[u + r], i, "rp", m),
                g(t[u + s], i, "rpe", m),
                g(t.domLoading, i, "dl", m),
                g(t.domInteractive, i, "di", m),
                g(t[l + r], i, "ds", m),
                g(t[l + s], i, "de", m),
                g(t.domComplete, i, "dc", m),
                g(t[d + r], i, "l", m),
                g(t[d + s], i, "le", m),
                i
        }
        function p(e, t) {
            var i;
            return g("number" == typeof (i = e.type) ? i : {
                navigate: void 0,
                reload: 1,
                back_forward: 2,
                prerender: 3
            }[i], t, "ty"),
            g(e.redirectCount, t, "rc"),
            t
        }
        function g(e, t, i, r) {
            if ("number" == typeof e && e > 0) {
                if (r) {
                    const i = t?.of > 0 ? t.of : 0;
                    e = Math.max(e - i, 0)
                }
                e = Math.round(e),
                t[i] = e,
                m.push(e)
            } else
                m.push(void 0)
        }
    }
    ,
    9119: (e, t, i) => {
        i.d(t, {
            L: () => n
        });
        var r = /([^?#]*)[^#]*(#[^?]*|$).*/
          , s = /([^?#]*)().*/;
        function n(e, t) {
            return e.replace(t ? r : s, "$1$2")
        }
    }
    ,
    3762: (e, t, i) => {
        i.d(t, {
            WL: () => h,
            uR: () => u
        });
        var r = i(3304)
          , s = {
            "%2C": ",",
            "%3A": ":",
            "%2F": "/",
            "%40": "@",
            "%24": "$",
            "%3B": ";"
        }
          , n = Object.keys(s)
          , a = new RegExp(n.join("|"),"g");
        function o(e) {
            return s[e]
        }
        function c(e) {
            return null == e ? "null" : encodeURIComponent(e).replace(a, o)
        }
        function h(e, t) {
            var i = 0
              , s = "";
            return Object.entries(e || {}).forEach(( ([e,n]) => {
                var a, o, h = [];
                if ("string" == typeof n || !Array.isArray(n) && null != n && n.toString().length)
                    a = "&" + e + "=" + c(n),
                    i += a.length,
                    s += a;
                else if (Array.isArray(n) && n.length) {
                    for (i += 9,
                    o = 0; o < n.length && (a = c((0,
                    r.A)(n[o])),
                    i += a.length,
                    !(void 0 !== t && i >= t)); o++)
                        h.push(a);
                    s += "&" + e + "=%5B" + h.join(",") + "%5D"
                }
            }
            )),
            s
        }
        function u(e, t, i={}) {
            return Object.keys(i).includes(e) ? "" : t && "string" == typeof t ? "&" + e + "=" + c(t) : ""
        }
    }
    ,
    4284: (e, t, i) => {
        i.d(t, {
            p: () => s
        });
        var r = i(6154);
        function s() {
            return Boolean("file:" === r.gm?.location?.protocol)
        }
    }
    ,
    9422: (e, t, i) => {
        i.d(t, {
            Jf: () => n,
            mj: () => s,
            nF: () => a
        });
        var r = i(6154);
        function s({isFinalHarvest: e=!1}={}) {
            return e && r.RI ? o : "undefined" != typeof XMLHttpRequest ? a : n
        }
        function n({url: e, body: t=null, method: i="POST", headers: r=[{
            key: "content-type",
            value: "text/plain"
        }]}) {
            const s = {};
            for (const e of r)
                s[e.key] = e.value;
            return fetch(e, {
                headers: s,
                method: i,
                body: t,
                credentials: "include"
            })
        }
        function a({url: e, body: t=null, sync: i, method: r="POST", headers: s=[{
            key: "content-type",
            value: "text/plain"
        }]}) {
            const n = new XMLHttpRequest;
            n.open(r, e, !i);
            try {
                "withCredentials"in n && (n.withCredentials = !0)
            } catch (e) {}
            return s.forEach((e => {
                n.setRequestHeader(e.key, e.value)
            }
            )),
            n.send(t),
            n
        }
        function o({url: e, body: t}) {
            try {
                return window.navigator.sendBeacon.bind(window.navigator)(e, t)
            } catch (e) {
                return !1
            }
        }
    }
    ,
    3311: (e, t, i) => {
        function r(e, t, i="string", s=[]) {
            return e && "object" == typeof e ? (Object.keys(e).forEach((n => {
                "object" == typeof e[n] ? r(e[n], t, i, s) : typeof e[n] !== i || s.includes(n) || (e[n] = t(e[n]))
            }
            )),
            e) : e
        }
        i.d(t, {
            G: () => r
        })
    }
    ,
    1083: (e, t, i) => {
        i.d(t, {
            w: () => r
        });
        const r = {
            FIRST_PAINT: "fp",
            FIRST_CONTENTFUL_PAINT: "fcp",
            FIRST_INPUT_DELAY: "fi",
            LARGEST_CONTENTFUL_PAINT: "lcp",
            CUMULATIVE_LAYOUT_SHIFT: "cls",
            INTERACTION_TO_NEXT_PAINT: "inp",
            TIME_TO_FIRST_BYTE: "ttfb"
        }
    }
    ,
    5344: (e, t, i) => {
        i.d(t, {
            j: () => a
        });
        var r = i(7226)
          , s = i(6154)
          , n = i(1083);
        const a = new (i(6773).x)(n.w.FIRST_CONTENTFUL_PAINT);
        if (s.RI)
            if (s.sb)
                try {
                    if (!s.mw) {
                        performance.getEntriesByType("paint").forEach((e => {
                            "first-contentful-paint" === e.name && a.update({
                                value: Math.floor(e.startTime)
                            })
                        }
                        ))
                    }
                } catch (e) {}
            else
                (0,
                r.zB)(( ({value: e, attribution: t}) => {
                    if (s.mw || a.isValid)
                        return;
                    const i = {
                        timeToFirstByte: t.timeToFirstByte,
                        firstByteToFCP: t.firstByteToFCP,
                        loadState: t.loadState
                    };
                    a.update({
                        value: e,
                        attrs: i
                    })
                }
                ))
    }
    ,
    5181: (e, t, i) => {
        i.d(t, {
            J: () => n
        });
        var r = i(6154)
          , s = i(1083);
        const n = new (i(6773).x)(s.w.FIRST_PAINT);
        if (r.RI) {
            const e = e => {
                e.forEach((e => {
                    "first-paint" !== e.name || n.isValid || (t.disconnect(),
                    n.update({
                        value: e.startTime
                    }))
                }
                ))
            }
            ;
            let t;
            try {
                PerformanceObserver.supportedEntryTypes.includes("paint") && !r.mw && (t = new PerformanceObserver((t => {
                    Promise.resolve().then(( () => {
                        e(t.getEntries())
                    }
                    ))
                }
                )),
                t.observe({
                    type: "paint",
                    buffered: !0
                }))
            } catch (e) {}
        }
    }
    ,
    8779: (e, t, i) => {
        i.d(t, {
            j: () => o
        });
        var r = i(6154)
          , s = i(1083)
          , n = i(6773)
          , a = i(7226);
        const o = new n.x(s.w.TIME_TO_FIRST_BYTE);
        if (r.RI && "undefined" != typeof PerformanceNavigationTiming && !r.OF && window === window.parent)
            (0,
            a.Ck)(( ({value: e, attribution: t}) => {
                o.isValid || o.update({
                    value: e,
                    attrs: {
                        navigationEntry: t.navigationEntry
                    }
                })
            }
            ));
        else if (!o.isValid) {
            const e = {};
            for (let t in r.gm?.performance?.timing || {})
                e[t] = Math.max(r.gm?.performance?.timing[t] - r.WN, 0);
            o.update({
                value: e.responseStart,
                attrs: {
                    navigationEntry: e
                }
            })
        }
    }
    ,
    6773: (e, t, i) => {
        i.d(t, {
            x: () => r
        });
        class r {
            #r = new Set;
            history = [];
            constructor(e, t) {
                this.name = e,
                this.attrs = {},
                this.roundingMethod = "function" == typeof t ? t : Math.floor
            }
            update({value: e, attrs: t={}}) {
                if (null == e || e < 0)
                    return;
                const i = {
                    value: this.roundingMethod(e),
                    name: this.name,
                    attrs: t
                };
                this.history.push(i),
                this.#r.forEach((e => {
                    try {
                        e(i)
                    } catch (e) {}
                }
                ))
            }
            get current() {
                return this.history[this.history.length - 1] || {
                    value: void 0,
                    name: this.name,
                    attrs: {}
                }
            }
            get isValid() {
                return this.current.value >= 0
            }
            subscribe(e, t=!0) {
                if ("function" == typeof e)
                    return this.#r.add(e),
                    this.isValid && t && this.history.forEach((t => {
                        e(t)
                    }
                    )),
                    () => {
                        this.#r.delete(e)
                    }
            }
        }
    }
    ,
    1038: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => v
        });
        var r = i(3606)
          , s = i(3304)
          , n = i(9908)
          , a = i(1140)
          , o = i(7295)
          , c = i(9300)
          , h = i(860)
          , u = i(3969)
          , d = i(5942);
        function l({body: e, query: t}={}) {
            if (e || t)
                try {
                    const i = function(e) {
                        if (!e)
                            return;
                        Array.isArray(e) || (e = [e]);
                        const t = []
                          , i = [];
                        for (let r of e) {
                            const e = m(r);
                            e && (t.push(e.operationName),
                            i.push(e.operationType))
                        }
                        if (!i.length)
                            return;
                        return {
                            operationName: t.join(","),
                            operationType: i.join(","),
                            operationFramework: "GraphQL"
                        }
                    }(f(e));
                    if (i)
                        return i;
                    const r = m(function(e) {
                        if (!e || "string" != typeof e)
                            return;
                        const t = new URLSearchParams(e);
                        return f(Object.fromEntries(t))
                    }(t));
                    if (r)
                        return r
                } catch (e) {}
        }
        function m(e) {
            if ("object" != typeof e || !e.query || "string" != typeof e.query)
                return;
            const t = e.query.trim().match(/^(query|mutation|subscription)\s?(\w*)/)
              , i = t?.[1];
            if (!i)
                return;
            return {
                operationName: e.operationName || t?.[2] || "Anonymous",
                operationType: i,
                operationFramework: "GraphQL"
            }
        }
        function f(e) {
            let t;
            if (!e || "string" != typeof e && "object" != typeof e)
                return;
            if (t = "string" == typeof e ? JSON.parse(e) : e,
            i = t,
            i?.constructor !== {}.constructor && !Array.isArray(t))
                return;
            var i;
            let r = !1;
            return r = Array.isArray(t) ? t.some((e => p(e))) : p(t),
            r ? t : void 0
        }
        function p(e) {
            return !("object" != typeof e || !e.query || "string" != typeof e.query)
        }
        var g = i(5519);
        class v extends d.r {
            static featureName = c.T;
            constructor(e) {
                super(e, c.T);
                const t = e.init.ajax.harvestTimeSeconds || 10;
                (0,
                o.Xv)(e.runtime.denyList),
                this.underSpaEvents = {};
                const i = this;
                this.ee.on("interactionDone", ( (e, t) => {
                    this.underSpaEvents[e.id] && (t || this.underSpaEvents[e.id].forEach((e => this.events.add(e))),
                    delete this.underSpaEvents[e.id])
                }
                )),
                (0,
                r.i)("returnAjax", (e => this.events.add(e)), this.featureName, this.ee),
                (0,
                r.i)("xhr", (function() {
                    i.storeXhr(...arguments, this)
                }
                ), this.featureName, this.ee),
                this.waitForFlags([]).then(( () => {
                    new a.n(h.$J[this.featureName],{
                        onFinished: e => this.postHarvestCleanup(e.sent && e.retry),
                        getPayload: e => this.makeHarvestPayload(e.retry)
                    },this).startTimer(t),
                    this.drain()
                }
                ))
            }
            storeXhr(e, t, i, r, a, c) {
                let d;
                t.time = i,
                d = e.cat ? (0,
                s.A)([e.status, e.cat]) : (0,
                s.A)([e.status, e.host, e.pathname]);
                const m = (0,
                o.gX)(e)
                  , f = this.agentRef.init.feature_flags?.includes("ajax_metrics_deny_list");
                if (!Boolean(this.agentRef.features?.[h.K7.jserrors]) || !m && f || this.agentRef.sharedAggregator.add("xhr", d, e, t),
                !m)
                    return void (e.hostname === this.agentRef.info.errorBeacon || this.agentRef.init.proxy?.beacon && e.hostname === this.agentRef.init.proxy.beacon ? ((0,
                    n.p)(u.xV, ["Ajax/Events/Excluded/Agent"], void 0, h.K7.metrics, this.ee),
                    f && (0,
                    n.p)(u.xV, ["Ajax/Metrics/Excluded/Agent"], void 0, h.K7.metrics, this.ee)) : ((0,
                    n.p)(u.xV, ["Ajax/Events/Excluded/App"], void 0, h.K7.metrics, this.ee),
                    f && (0,
                    n.p)(u.xV, ["Ajax/Metrics/Excluded/App"], void 0, h.K7.metrics, this.ee)));
                (0,
                n.p)("bstXhrAgg", ["xhr", d, e, t], void 0, h.K7.sessionTrace, this.ee);
                const p = {
                    method: e.method,
                    status: e.status,
                    domain: e.host,
                    path: e.pathname,
                    requestSize: t.txSize,
                    responseSize: t.rxSize,
                    type: a,
                    startTime: i,
                    endTime: r,
                    callbackDuration: t.cbTime
                };
                c.dt && (p.spanId = c.dt.spanId,
                p.traceId = c.dt.traceId,
                p.spanTimestamp = Math.floor(this.agentRef.runtime.timeKeeper.correctAbsoluteTimestamp(c.dt.timestamp))),
                p.gql = e.gql = l({
                    body: c.body,
                    query: c.parsedOrigin?.search
                }),
                p.gql && (0,
                n.p)(u.xV, ["Ajax/Events/GraphQL/Bytes-Added", (0,
                s.A)(p.gql).length], void 0, h.K7.metrics, this.ee);
                if (Boolean(this.agentRef.features?.[h.K7.softNav]))
                    (0,
                    n.p)("ajax", [p], void 0, h.K7.softNav, this.ee);
                else if (c.spaNode) {
                    const e = c.spaNode.interaction.id;
                    this.underSpaEvents[e] ??= [],
                    this.underSpaEvents[e].push(p)
                } else
                    this.events.add(p)
            }
            serializer(e) {
                const t = (0,
                g.uJ)(this.agentIdentifier);
                let i = "bel.7;";
                for (let r = 0; r < e.length; r++) {
                    const s = e[r]
                      , n = [(0,
                    g.sH)(s.startTime), (0,
                    g.sH)(s.endTime - s.startTime), (0,
                    g.sH)(0), (0,
                    g.sH)(0), t(s.method), (0,
                    g.sH)(s.status), t(s.domain), t(s.path), (0,
                    g.sH)(s.requestSize), (0,
                    g.sH)(s.responseSize), "fetch" === s.type ? 1 : "", t(0), (0,
                    g.me)(s.spanId, t, !0) + (0,
                    g.me)(s.traceId, t, !0) + (0,
                    g.me)(s.spanTimestamp, g.sH, !1)];
                    let a = "2,";
                    const o = this.agentRef.info.jsAttributes
                      , c = (0,
                    g.AQ)({
                        ...o || {},
                        ...s.gql || {}
                    }, t);
                    n.unshift((0,
                    g.sH)(c.length)),
                    a += n.join(","),
                    c && c.length > 0 && (a += ";" + c.join(";")),
                    r + 1 < e.length && (a += ";"),
                    i += a
                }
                return i
            }
        }
    }
    ,
    8019: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => y
        });
        var r = i(3304)
          , s = i(1140)
          , n = i(9119)
          , a = i(3333)
          , o = i(6154)
          , c = i(5942)
          , h = i(944)
          , u = i(1863)
          , d = i(3606)
          , l = i(3969)
          , m = i(3311)
          , f = i(860);
        class p {
            constructor(e, t) {
                this.event = e,
                this.count = 1,
                this.originMs = Math.floor(e.timeStamp),
                this.relativeMs = [0],
                this.selectorPath = t,
                this.rageClick = void 0
            }
            aggregate(e) {
                this.count++,
                this.relativeMs.push(Math.floor(e.timeStamp - this.originMs)),
                this.isRageClick() && (this.rageClick = !0)
            }
            isRageClick() {
                const e = this.relativeMs.length;
                return "click" === this.event.type && e >= a.nf && this.relativeMs[e - 1] - this.relativeMs[e - a.nf] < a.mq
            }
        }
        class g {
            #s = void 0;
            #n = "";
            get aggregationEvent() {
                const e = this.#s;
                return this.#n = "",
                this.#s = void 0,
                e
            }
            process(e) {
                if (!e)
                    return;
                const t = function(e) {
                    let t;
                    t = a.qN.includes(e.type) || e.target === window ? "window" : e.target === document ? "document" : (e => {
                        if (!e)
                            return;
                        let t = ""
                          , i = (e => {
                            try {
                                let t = 1;
                                const {tagName: i} = e;
                                for (; e.previousElementSibling; )
                                    e.previousElementSibling.tagName === i && t++,
                                    e = e.previousElementSibling;
                                return t
                            } catch (e) {}
                        }
                        )(e);
                        try {
                            for (; e?.tagName; ) {
                                const {id: i, localName: r} = e;
                                t = [r, i ? "#".concat(i) : "", t ? ">".concat(t) : ""].join(""),
                                e = e.parentNode
                            }
                        } catch (e) {}
                        return t ? i ? "".concat(t, ":nth-of-type(").concat(i, ")") : t : void 0
                    }
                    )(e.target);
                    return t
                }(e)
                  , i = function(e, t) {
                    let i = e.type;
                    "scrollend" !== e.type && (i += "-" + t);
                    return i
                }(e, t);
                if (!i || i !== this.#n) {
                    const r = this.#s;
                    return this.#n = i,
                    this.#s = new p(e,t),
                    r
                }
                this.#s.aggregate(e)
            }
        }
        var v = i(2123);
        class y extends c.r {
            static featureName = a.TZ;
            constructor(e) {
                super(e, a.TZ),
                this.eventsPerHarvest = 1e3,
                this.harvestTimeSeconds = e.init.generic_events.harvestTimeSeconds,
                this.referrerUrl = o.RI && document.referrer ? (0,
                n.L)(document.referrer) : void 0,
                this.waitForFlags(["ins"]).then(( ([t]) => {
                    if (!t)
                        return this.blocked = !0,
                        void this.deregisterDrain();
                    let i;
                    e.init.page_action.enabled && (0,
                    d.i)("api-addPageAction", ( (e, t, i) => {
                        this.addEvent({
                            ...i,
                            eventType: "PageAction",
                            timestamp: Math.floor(this.agentRef.runtime.timeKeeper.correctRelativeTimestamp(e)),
                            timeSinceLoad: e / 1e3,
                            actionName: t,
                            referrerUrl: this.referrerUrl,
                            ...o.RI && {
                                browserWidth: window.document.documentElement?.clientWidth,
                                browserHeight: window.document.documentElement?.clientHeight
                            }
                        })
                    }
                    ), this.featureName, this.ee),
                    o.RI && e.init.user_actions.enabled && (this.userActionAggregator = new g,
                    i = e => {
                        try {
                            if (e?.event) {
                                const {target: t, timeStamp: i, type: r} = e.event;
                                this.addEvent({
                                    eventType: "UserAction",
                                    timestamp: Math.floor(this.agentRef.runtime.timeKeeper.correctRelativeTimestamp(i)),
                                    action: r,
                                    actionCount: e.count,
                                    actionDuration: e.relativeMs[e.relativeMs.length - 1],
                                    actionMs: e.relativeMs,
                                    rageClick: e.rageClick,
                                    target: e.selectorPath,
                                    ...(0,
                                    v.v)(window) && {
                                        iframe: !0
                                    },
                                    ...t?.id && {
                                        targetId: t.id
                                    },
                                    ...t?.tagName && {
                                        targetTag: t.tagName
                                    },
                                    ...t?.type && {
                                        targetType: t.type
                                    },
                                    ...t?.className && {
                                        targetClass: t.className
                                    }
                                })
                            }
                        } catch (e) {}
                    }
                    ,
                    (0,
                    d.i)("ua", (e => {
                        i(this.userActionAggregator.process(e))
                    }
                    ), this.featureName, this.ee));
                    const r = [...e.init.performance.capture_marks ? ["mark"] : [], ...e.init.performance.capture_measures ? ["measure"] : []];
                    if (r.length)
                        try {
                            r.forEach((t => {
                                if (PerformanceObserver.supportedEntryTypes.includes(t)) {
                                    new PerformanceObserver((i => {
                                        i.getEntries().forEach((i => {
                                            try {
                                                this.addEvent({
                                                    eventType: "BrowserPerformance",
                                                    timestamp: Math.floor(e.runtime.timeKeeper.correctRelativeTimestamp(i.startTime)),
                                                    entryName: i.name,
                                                    entryDuration: i.duration,
                                                    entryType: t,
                                                    ...i.detail && {
                                                        entryDetail: i.detail
                                                    }
                                                })
                                            } catch (e) {}
                                        }
                                        ))
                                    }
                                    )).observe({
                                        buffered: !0,
                                        type: t
                                    })
                                }
                            }
                            ))
                        } catch (e) {}
                    this.harvestScheduler = new s.n(f.$J[this.featureName],{
                        onFinished: e => this.postHarvestCleanup(e.sent && e.retry),
                        onUnload: () => i?.(this.userActionAggregator.aggregationEvent)
                    },this),
                    this.harvestScheduler.harvest.on(f.$J[this.featureName], (e => this.makeHarvestPayload(e.retry))),
                    this.harvestScheduler.startTimer(this.harvestTimeSeconds, 0),
                    this.drain()
                }
                ))
            }
            addEvent(e={}) {
                if (!e || !Object.keys(e).length)
                    return;
                if (!e.eventType)
                    return void (0,
                    h.R)(44);
                for (let t in e) {
                    let i = e[t];
                    e[t] = i && "object" == typeof i ? (0,
                    r.A)(i) : i
                }
                const t = {
                    timestamp: Math.floor(this.agentRef.runtime.timeKeeper.correctRelativeTimestamp((0,
                    u.t)())),
                    pageUrl: (0,
                    n.L)("" + o.m),
                    currentUrl: (0,
                    n.L)("" + location)
                }
                  , i = {
                    ...this.agentRef.info.jsAttributes || {},
                    ...t,
                    ...e
                };
                this.events.add(i) || this.events.isEmpty() || (this.ee.emit(l.xV, ["GenericEvents/Harvest/Max/Seen"]),
                this.harvestScheduler.runHarvest(),
                this.events.add(i))
            }
            serializer(e) {
                return (0,
                m.G)({
                    ins: e
                }, this.obfuscator.obfuscateString.bind(this.obfuscator), "string")
            }
            queryStringsBuilder() {
                return {
                    ua: this.agentRef.info.userAttributes,
                    at: this.agentRef.info.atts
                }
            }
        }
    }
    ,
    5928: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => F
        });
        const r = /([a-z0-9]+)$/i;
        function s(e) {
            if (!e)
                return;
            const t = e.match(r);
            return t ? t[1] : void 0
        }
        var n = /^\n+|\n+$/g;
        function a(e) {
            return function(e) {
                var t;
                if (e.length > 100) {
                    var i = e.length - 100;
                    t = e.slice(0, 50).join("\n"),
                    t += "\n< ...truncated " + i + " lines... >\n",
                    t += e.slice(-50).join("\n")
                } else
                    t = e.join("\n");
                return t
            }(e).replace(n, "")
        }
        var o = i(6154)
          , c = i(9119);
        function h(e) {
            if ("string" != typeof e)
                return "";
            const t = (0,
            c.L)(e);
            return t === (0,
            c.L)(o.m) ? "<inline>" : t
        }
        var u = !1
          , d = /function (.+?)\s*\(/
          , l = /^\s*at (?:((?:\[object object\])?(?:[^(]*\([^)]*\))*[^()]*(?: \[as \S+\])?) )?\(?((?:file|http|https|chrome-extension):.*?)?:(\d+)(?::(\d+))?\)?\s*$/i
          , m = /^\s*(?:(\S*|global code)(?:\(.*?\))?@)?((?:file|http|https|chrome|safari-extension).*?):(\d+)(?::(\d+))?\s*$/i
          , f = /^\s*at .+ \(eval at \S+ \((?:(?:file|http|https):[^)]+)?\)(?:, [^:]*:\d+:\d+)?\)$/i
          , p = /^\s*at Function code \(Function code:\d+:\d+\)\s*/i;
        function g(e) {
            var t = null;
            try {
                if (t = function(e) {
                    if (!e.stack)
                        return null;
                    var t = e.stack.split("\n").reduce(v, {
                        frames: [],
                        stackLines: [],
                        wrapperSeen: !1
                    });
                    return t.frames.length ? {
                        mode: "stack",
                        name: e.name || y(e),
                        message: e.message,
                        stackString: a(t.stackLines),
                        frames: t.frames
                    } : null
                }(e),
                t)
                    return t
            } catch (e) {
                u
            }
            try {
                if (t = function(e) {
                    if (!("line"in e))
                        return null;
                    var t = e.name || y(e);
                    if (!e.sourceURL)
                        return {
                            mode: "sourceline",
                            name: t,
                            message: e.message,
                            stackString: t + ": " + e.message + "\n    in evaluated code",
                            frames: [{
                                func: "evaluated code"
                            }]
                        };
                    var i = h(e.sourceURL)
                      , r = t + ": " + e.message + "\n    at " + i;
                    e.line && (r += ":" + e.line,
                    e.column && (r += ":" + e.column));
                    return {
                        mode: "sourceline",
                        name: t,
                        message: e.message,
                        stackString: r,
                        frames: [{
                            url: i,
                            line: e.line,
                            column: e.column
                        }]
                    }
                }(e),
                t)
                    return t
            } catch (e) {
                u
            }
            try {
                if (t = function(e) {
                    var t = e.name || y(e);
                    return t ? {
                        mode: "nameonly",
                        name: t,
                        message: e.message,
                        stackString: t + ": " + e.message,
                        frames: []
                    } : null
                }(e),
                t)
                    return t
            } catch (e) {
                u
            }
            return {
                mode: "failed",
                stackString: "",
                frames: []
            }
        }
        function v(e, t) {
            let i = function(e) {
                var t = e.match(m);
                t || (t = e.match(l));
                if (t)
                    return {
                        url: t[2],
                        func: "Anonymous function" !== t[1] && "global code" !== t[1] && t[1] || null,
                        line: +t[3],
                        column: t[4] ? +t[4] : null
                    };
                if (e.match(f) || e.match(p) || "anonymous" === e)
                    return {
                        func: "evaluated code"
                    }
            }(t);
            if (!i)
                return e.stackLines.push(t),
                e;
            var r;
            if ((r = i.func) && r.indexOf("nrWrapper") >= 0 && (e.wrapperSeen = !0),
            !e.wrapperSeen) {
                let r = h(i.url);
                r !== i.url && (t = t.replace(i.url, r),
                i.url = r),
                e.stackLines.push(t),
                e.frames.push(i)
            }
            return e
        }
        function y(e) {
            var t = d.exec(String(e.constructor));
            return t && t.length > 1 ? t[1] : "unknown"
        }
        function b(e) {
            var t = 0;
            if (!e || !e.length)
                return t;
            for (var i = 0; i < e.length; i++)
                t = (t << 5) - t + e.charCodeAt(i),
                t |= 0;
            return t
        }
        var T = i(3606)
          , S = i(1140)
          , w = i(3304)
          , R = i(9908)
          , N = i(6774)
          , E = i(860)
          , I = i(5942)
          , A = i(1863)
          , x = i(3311);
        const k = "Rrweb"
          , M = "Security-Policy";
        var C = i(3969);
        class F extends I.r {
            static featureName = N.T;
            constructor(e) {
                super(e, N.T),
                this.stackReported = {},
                this.observedAt = {},
                this.pageviewReported = {},
                this.bufferedErrorsUnderSpa = {},
                this.errorOnPage = !1,
                this.ee.on("interactionDone", ( (e, t) => this.onInteractionDone(e, t))),
                (0,
                T.i)("err", ( (...e) => this.storeError(...e)), this.featureName, this.ee),
                (0,
                T.i)("ierr", ( (...e) => this.storeError(...e)), this.featureName, this.ee),
                (0,
                T.i)("softNavFlush", ( (e, t, i) => this.onSoftNavNotification(e, t, i)), this.featureName, this.ee);
                const t = e.init.jserrors.harvestTimeSeconds || 10
                  , i = ["err", "ierr", "xhr"];
                this.waitForFlags(["err"]).then(( ([e]) => {
                    if (e) {
                        const e = new S.n(E.$J[this.featureName],{
                            onFinished: e => this.postHarvestCleanup(e.sent && e.retry, {
                                aggregatorTypes: i
                            })
                        },this);
                        e.harvest.on(E.$J[this.featureName], (e => this.makeHarvestPayload(e.retry, {
                            aggregatorTypes: i
                        }))),
                        e.startTimer(t),
                        this.drain()
                    } else
                        this.blocked = !0,
                        this.deregisterDrain()
                }
                ))
            }
            serializer(e) {
                return (0,
                x.G)(e, this.obfuscator.obfuscateString.bind(this.obfuscator), "string")
            }
            queryStringsBuilder(e) {
                const t = {}
                  , i = (0,
                w.A)(this.agentRef.runtime.releaseIds);
                return "{}" !== i && (t.ri = i),
                e?.err?.length && (this.errorOnPage || (t.pve = "1",
                this.errorOnPage = !0),
                this.agentRef.features?.[E.K7.sessionReplay]?.featAggregate?.replayIsActive() || e.err.forEach((e => delete e.params.hasReplay))),
                t
            }
            buildCanonicalStackString(e) {
                for (var t = "", i = 0; i < e.frames.length; i++) {
                    var r = e.frames[i]
                      , n = s(r.func);
                    t && (t += "\n"),
                    n && (t += n + "@"),
                    "string" == typeof r.url && (t += r.url),
                    r.line && (t += ":" + r.line)
                }
                return t
            }
            storeError(e, t, i, r, s) {
                if (!e)
                    return;
                let n;
                if (t = t || (0,
                A.t)(),
                !i && this.agentRef.runtime.onerror && (n = this.agentRef.runtime.onerror(e),
                n && ("string" != typeof n.group || !n.group.length)))
                    return;
                var a = g(e);
                const {shouldSwallow: c, reason: h} = function(e, t) {
                    const i = {
                        shouldSwallow: t || !1,
                        reason: "Other"
                    }
                      , r = e.frames?.[0];
                    if (!r || "string" != typeof e?.message)
                        return i;
                    const s = r?.url?.match(/nr-(.*)-recorder.min.js/)
                      , n = r?.url?.match(/rrweb/)
                      , a = r?.url?.match(/recorder/)
                      , o = e.message.toLowerCase().match(/an attempt was made to break through the security policy of the user agent/);
                    return s || n ? (i.shouldSwallow = !0,
                    i.reason = k,
                    o && (i.reason += "-" + M)) : a && o && (i.shouldSwallow = !0,
                    i.reason = k + "-" + M),
                    i
                }(a, i);
                if (c)
                    return void (0,
                    R.p)(C.xV, ["Internal/Error/" + h], void 0, E.K7.metrics, this.ee);
                const u = {
                    stackHash: b(this.buildCanonicalStackString(a)),
                    exceptionClass: a.name,
                    request_uri: o.gm?.location.pathname
                };
                a.message && (u.message = "" + a.message),
                n?.group && (u.errorGroup = n.group),
                s && (u.hasReplay = s);
                var d, l = b("".concat(a.name, "_").concat(a.message, "_").concat(a.stackString, "_").concat(u.hasReplay ? 1 : 0));
                this.stackReported[l] ? u.browser_stack_hash = b(a.stackString) : (this.stackReported[l] = !0,
                u.stack_trace = (d = a.stackString).length > 65530 ? d.substr(0, 65530) : d,
                this.observedAt[l] = Math.floor(this.agentRef.runtime.timeKeeper.correctRelativeTimestamp(t))),
                u.releaseIds = (0,
                w.A)(this.agentRef.runtime.releaseIds),
                this.pageviewReported[l] || (u.pageview = 1,
                this.pageviewReported[l] = !0),
                u.firstOccurrenceTimestamp = this.observedAt[l],
                u.timestamp = Math.floor(this.agentRef.runtime.timeKeeper.correctRelativeTimestamp(t));
                const m = ["err", l, u, {
                    time: t
                }, r];
                if ((0,
                R.p)("trace-jserror", m, void 0, E.K7.sessionTrace, this.ee),
                this.blocked)
                    return;
                e?.__newrelic?.[this.agentIdentifier] && (u._interactionId = e.__newrelic[this.agentIdentifier].interactionId,
                u._interactionNodeId = e.__newrelic[this.agentIdentifier].interactionNodeId);
                Boolean(this.agentRef.features?.[E.K7.softNav]) ? (0,
                R.p)("jserror", [u, t], void 0, E.K7.softNav, this.ee) : (0,
                R.p)("spa-jserror", m, void 0, E.K7.spa, this.ee),
                u.browserInteractionId && !u._softNavFinished ? (this.bufferedErrorsUnderSpa[u.browserInteractionId] ??= [],
                this.bufferedErrorsUnderSpa[u.browserInteractionId].push(m)) : null != u._interactionId ? (this.bufferedErrorsUnderSpa[u._interactionId] = this.bufferedErrorsUnderSpa[u._interactionId] || [],
                this.bufferedErrorsUnderSpa[u._interactionId].push(m)) : this.#a(m, void 0 !== u.browserInteractionId, u._softNavAttributes)
            }
            #a(e, t, i={}) {
                let[r,s,n,a,o] = e;
                const c = {};
                t ? (Object.entries(i).forEach(( ([e,t]) => u(e, t))),
                s += n.browserInteractionId,
                delete n._softNavAttributes,
                delete n._softNavFinished) : (Object.entries(this.agentRef.info.jsAttributes).forEach(( ([e,t]) => u(e, t))),
                delete n.browserInteractionId),
                o && Object.entries(o).forEach(( ([e,t]) => u(e, t)));
                const h = s + ":" + b((0,
                w.A)(c));
                function u(e, t) {
                    c[e] = t && "object" == typeof t ? (0,
                    w.A)(t) : t
                }
                this.events.add(r, h, n, a, c)
            }
            onInteractionDone(e, t) {
                this.bufferedErrorsUnderSpa[e.id] && !this.blocked && (this.bufferedErrorsUnderSpa[e.id].forEach((i => {
                    var r = {};
                    const s = i[4];
                    Object.entries(e.root.attrs.custom || {}).forEach(o),
                    Object.entries(s || {}).forEach(o);
                    var n = i[2];
                    t && (n.browserInteractionId = e.root.attrs.id,
                    n._interactionNodeId && (n.parentNodeId = n._interactionNodeId.toString())),
                    delete n._interactionId,
                    delete n._interactionNodeId;
                    var a = (t ? i[1] + e.root.attrs.id : i[1]) + ":" + b((0,
                    w.A)(r));
                    function o([e,t]) {
                        r[e] = t && "object" == typeof t ? (0,
                        w.A)(t) : t
                    }
                    this.events.add(i[0], a, n, i[3], r)
                }
                )),
                delete this.bufferedErrorsUnderSpa[e.id])
            }
            onSoftNavNotification(e, t, i) {
                this.blocked || (this.bufferedErrorsUnderSpa[e]?.forEach((e => this.#a(e, t, i))),
                delete this.bufferedErrorsUnderSpa[e])
            }
        }
    }
    ,
    5288: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => y
        });
        var r = i(9908)
          , s = i(3606)
          , n = i(1140)
          , a = i(944)
          , o = i(3304)
          , c = i(3969)
          , h = i(5942)
          , u = i(993)
          , d = i(6154)
          , l = i(9119);
        class m {
            timestamp;
            message;
            attributes;
            level;
            constructor(e, t, i={}, r=u.p_.INFO) {
                this.timestamp = e,
                this.message = t,
                this.attributes = {
                    ...i,
                    pageUrl: (0,
                    l.L)("" + d.m)
                },
                this.level = r.toUpperCase()
            }
        }
        var f = i(3785)
          , p = i(3311)
          , g = i(7699)
          , v = i(860);
        class y extends h.r {
            static featureName = u.TZ;
            constructor(e) {
                super(e, u.TZ),
                this.harvestTimeSeconds = e.init.logging.harvestTimeSeconds,
                this.waitForFlags([]).then(( () => {
                    this.scheduler = new n.n(v.$J[this.featureName],{
                        onFinished: e => this.postHarvestCleanup(e.sent && e.retry),
                        retryDelay: this.harvestTimeSeconds,
                        getPayload: e => this.makeHarvestPayload(e.retry),
                        raw: !0
                    },this),
                    (0,
                    s.i)(u.ET, this.handleLog.bind(this), this.featureName, this.ee),
                    this.drain(),
                    this.scheduler.startTimer(this.harvestTimeSeconds, 0)
                }
                ))
            }
            handleLog(e, t, i={}, s=u.p_.INFO) {
                if (this.blocked)
                    return;
                if (i && "object" == typeof i || (i = {}),
                "string" == typeof s && (s = s.toUpperCase()),
                !(0,
                f.b)(s))
                    return (0,
                    a.R)(30, s);
                try {
                    if ("string" != typeof t) {
                        const e = (0,
                        o.A)(t);
                        t = e && "{}" !== e ? e : String(t)
                    }
                } catch (e) {
                    return void (0,
                    a.R)(16, t)
                }
                if ("string" != typeof t || !t)
                    return (0,
                    a.R)(32);
                const n = new m(Math.floor(this.agentRef.runtime.timeKeeper.correctRelativeTimestamp(e)),t,i,s)
                  , h = n.message.length + (0,
                o.A)(n.attributes).length + n.level.length + 10
                  , d = "Logging/Harvest/Failed/Seen";
                if (h > g.I)
                    return (0,
                    r.p)(c.xV, [d, h]),
                    void (0,
                    a.R)(31, n.message.slice(0, 25) + "...");
                this.events.wouldExceedMaxSize(h) && ((0,
                r.p)(c.xV, ["Logging/Harvest/Early/Seen", this.events.bytes + h]),
                this.scheduler.runHarvest()),
                this.events.add(n) || ((0,
                r.p)(c.xV, [d, h]),
                (0,
                a.R)(31, n.message.slice(0, 25) + "..."))
            }
            serializer(e) {
                const t = this.agentRef.runtime.session;
                return [{
                    common: {
                        attributes: {
                            "entity.guid": this.agentRef.runtime.appMetadata?.agents?.[0]?.entityGuid,
                            ...t && {
                                session: t.state.value || "0",
                                hasReplay: 1 === t.state.sessionReplayMode,
                                hasTrace: 1 === t.state.sessionTraceMode
                            },
                            ptid: this.agentRef.runtime.ptid,
                            appId: this.agentRef.info.applicationID,
                            standalone: Boolean(this.agentRef.info.sa),
                            agentVersion: this.agentRef.runtime.version,
                            "instrumentation.provider": "browser",
                            "instrumentation.version": this.agentRef.runtime.version,
                            "instrumentation.name": this.agentRef.runtime.loaderType
                        }
                    },
                    logs: (0,
                    p.G)(e, this.obfuscator.obfuscateString.bind(this.obfuscator), "string")
                }]
            }
            queryStringsBuilder() {
                return {
                    browser_monitoring_key: this.agentRef.info.licenseKey
                }
            }
        }
    }
    ,
    8351: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => O
        });
        var r = i(3606)
          , s = i(1140)
          , n = i(3969)
          , a = i(6154);
        const o = "React"
          , c = "NextJS"
          , h = "Vue"
          , u = "NuxtJS"
          , d = "Angular"
          , l = "AngularUniversal"
          , m = "Svelte"
          , f = "SvelteKit"
          , p = "Preact"
          , g = "PreactSSR"
          , v = "AngularJS"
          , y = "Backbone"
          , b = "Ember"
          , T = "Meteor"
          , S = "Zepto"
          , w = "Jquery"
          , R = "MooTools"
          , N = "Qwik"
          , E = "Electron";
        function I() {
            if (!a.RI)
                return [];
            const e = [];
            try {
                (function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "React") || Object.prototype.hasOwnProperty.call(window, "ReactDOM") || Object.prototype.hasOwnProperty.call(window, "ReactRedux") || document.querySelector("[data-reactroot], [data-reactid]") || ( () => {
                            const e = document.querySelectorAll("body > div");
                            for (let t = 0; t < e.length; t++)
                                if (Object.prototype.hasOwnProperty.call(e[t], "_reactRootContainer"))
                                    return !0
                        }
                        )()
                    } catch (e) {
                        return !1
                    }
                }
                )() && (e.push(o),
                function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "next") && Object.prototype.hasOwnProperty.call(window.next, "version")
                    } catch (e) {
                        return !1
                    }
                }() && e.push(c)),
                function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "Vue")
                    } catch (e) {
                        return !1
                    }
                }() && (e.push(h),
                function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "$nuxt") && Object.prototype.hasOwnProperty.call(window.$nuxt, "nuxt")
                    } catch (e) {
                        return !1
                    }
                }() && e.push(u)),
                function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "ng") || document.querySelector("[ng-version]")
                    } catch (e) {
                        return !1
                    }
                }() && (e.push(d),
                function() {
                    try {
                        return document.querySelector("[ng-server-context]")
                    } catch (e) {
                        return !1
                    }
                }() && e.push(l)),
                function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "__svelte")
                    } catch (e) {
                        return !1
                    }
                }() && (e.push(m),
                function() {
                    try {
                        return !!Object.keys(window).find((e => e.startsWith("__sveltekit")))
                    } catch (e) {
                        return !1
                    }
                }() && e.push(f)),
                function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "preact")
                    } catch (e) {
                        return !1
                    }
                }() && (e.push(p),
                function() {
                    try {
                        return document.querySelector('script[type="__PREACT_CLI_DATA__"]')
                    } catch (e) {
                        return !1
                    }
                }() && e.push(g)),
                function() {
                    try {
                        return Object.prototype.hasOwnProperty.call(window, "angular") || document.querySelector(".ng-binding, [ng-app], [data-ng-app], [ng-controller], [data-ng-controller], [ng-repeat], [data-ng-repeat]") || document.querySelector('script[src*="angular.js"], script[src*="angular.min.js"]')
                    } catch (e) {
                        return !1
                    }
                }() && e.push(v),
                Object.prototype.hasOwnProperty.call(window, "Backbone") && e.push(y),
                Object.prototype.hasOwnProperty.call(window, "Ember") && e.push(b),
                Object.prototype.hasOwnProperty.call(window, "Meteor") && e.push(T),
                Object.prototype.hasOwnProperty.call(window, "Zepto") && e.push(S),
                Object.prototype.hasOwnProperty.call(window, "jQuery") && e.push(w),
                Object.prototype.hasOwnProperty.call(window, "MooTools") && e.push(R),
                Object.prototype.hasOwnProperty.call(window, "qwikevents") && e.push(N),
                function() {
                    try {
                        return "object" == typeof navigator && "string" == typeof navigator.userAgent && navigator.userAgent.indexOf("Electron") >= 0
                    } catch (e) {
                        return !1
                    }
                }() && e.push(E)
            } catch (e) {}
            return e
        }
        var A = i(4284)
          , x = i(5289)
          , k = i(3878)
          , M = i(5942)
          , C = i(860)
          , F = i(2123);
        class O extends M.r {
            static featureName = n.TZ;
            constructor(e) {
                super(e, n.TZ);
                const t = ["cm", "sm"];
                this.waitForFlags(["err"]).then(( ([e]) => {
                    if (e) {
                        new s.n(C.$J[this.featureName],{
                            onUnload: () => this.unload()
                        },this).harvest.on(C.$J[this.featureName], ( () => this.makeHarvestPayload(void 0, {
                            aggregatorTypes: t
                        }))),
                        this.drain()
                    } else
                        this.blocked = !0,
                        this.deregisterDrain()
                }
                )),
                (0,
                r.i)(n.xV, this.storeSupportabilityMetrics.bind(this), this.featureName, this.ee),
                (0,
                r.i)(n.XG, this.storeEventMetrics.bind(this), this.featureName, this.ee),
                this.singleChecks(),
                this.eachSessionChecks()
            }
            storeSupportabilityMetrics(e, t) {
                if (this.blocked)
                    return;
                const i = n.rs
                  , r = {
                    name: e
                };
                this.events.addMetric(i, e, r, t)
            }
            storeEventMetrics(e, t) {
                if (this.blocked)
                    return;
                const i = n.z_
                  , r = {
                    name: e
                };
                this.events.add(i, e, r, t)
            }
            singleChecks() {
                const {distMethod: e, loaderType: t} = this.agentRef.runtime
                  , {proxy: i, privacy: r} = this.agentRef.init;
                if (t && this.storeSupportabilityMetrics("Generic/LoaderType/".concat(t, "/Detected")),
                e && this.storeSupportabilityMetrics("Generic/DistMethod/".concat(e, "/Detected")),
                a.RI) {
                    this.storeSupportabilityMetrics("Generic/Runtime/Browser/Detected");
                    const e = document?.currentScript?.nonce;
                    e && "" !== e && this.storeSupportabilityMetrics("Generic/Runtime/Nonce/Detected"),
                    (0,
                    x.sB)(( () => {
                        I().forEach((e => {
                            this.storeSupportabilityMetrics("Framework/" + e + "/Detected")
                        }
                        ))
                    }
                    )),
                    r.cookies_enabled || this.storeSupportabilityMetrics("Config/SessionTracking/Disabled")
                } else
                    a.bv ? this.storeSupportabilityMetrics("Generic/Runtime/Worker/Detected") : this.storeSupportabilityMetrics("Generic/Runtime/Unknown/Detected");
                (0,
                A.p)() && this.storeSupportabilityMetrics("Generic/FileProtocol/Detected");
                const s = this.obfuscator.ruleValidationCache;
                if (s.length > 0 && (this.storeSupportabilityMetrics("Generic/Obfuscate/Detected"),
                s.filter((e => !e.isValid)).length > 0 && this.storeSupportabilityMetrics("Generic/Obfuscate/Invalid")),
                i.assets && this.storeSupportabilityMetrics("Config/AssetsUrl/Changed"),
                i.beacon && this.storeSupportabilityMetrics("Config/BeaconUrl/Changed"),
                a.RI && window.MutationObserver) {
                    (0,
                    F.v)(window) && this.storeSupportabilityMetrics("Generic/Runtime/IFrame/Detected");
                    const e = window.document.querySelectorAll("video").length;
                    e && this.storeSupportabilityMetrics("Generic/VideoElement/Added", e);
                    const t = window.document.querySelectorAll("iframe").length;
                    t && this.storeSupportabilityMetrics("Generic/IFrame/Added", t);
                    new MutationObserver((e => {
                        e.forEach((e => {
                            e.addedNodes.forEach((e => {
                                e instanceof HTMLVideoElement && this.storeSupportabilityMetrics("Generic/VideoElement/Added", 1),
                                e instanceof HTMLIFrameElement && this.storeSupportabilityMetrics("Generic/IFrame/Added", 1)
                            }
                            ))
                        }
                        ))
                    }
                    )).observe(window.document.body, {
                        childList: !0,
                        subtree: !0
                    })
                }
            }
            eachSessionChecks() {
                a.RI && (0,
                k.sp)("pageshow", (e => {
                    e?.persisted && this.storeSupportabilityMetrics("Generic/BFCache/PageRestored")
                }
                ))
            }
            unload() {
                try {
                    if (this.resourcesSent)
                        return;
                    this.resourcesSent = !0;
                    const e = ["beacon", "fetch", "xmlhttprequest"]
                      , t = ["nr-data.net", "newrelic.com", "nr-local.net", "localhost"];
                    function i(t) {
                        return e.includes(t.initiatorType)
                    }
                    if ((performance?.getEntriesByType("resource") || []).forEach((e => {
                        var r;
                        r = e,
                        t.some((e => r.name.indexOf(e) >= 0)) ? i(e) ? this.storeSupportabilityMetrics("Generic/Resources/Ajax/Internal") : this.storeSupportabilityMetrics("Generic/Resources/Non-Ajax/Internal") : i(e) ? this.storeSupportabilityMetrics("Generic/Resources/Ajax/External") : this.storeSupportabilityMetrics("Generic/Resources/Non-Ajax/External")
                    }
                    )),
                    "undefined" != typeof performance) {
                        const r = performance.getEntriesByType("mark")
                          , s = performance.getEntriesByType("measure");
                        r.length && this.storeSupportabilityMetrics("Generic/Performance/Mark/Seen", r.length),
                        s.length && this.storeSupportabilityMetrics("Generic/Performance/Measure/Seen", s.length)
                    }
                } catch (n) {}
            }
        }
    }
    ,
    1983: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => w
        });
        var r = i(6154)
          , s = i(2733)
          , n = i(3304)
          , a = i(2555)
          , o = i(4624)
          , c = i(6630)
          , h = i(860)
          , u = i(384);
        function d(e) {
            const t = []
              , i = (0,
            u.Zm)();
            try {
                Object.keys(i.initializedAgents[e].features).forEach((e => {
                    switch (e) {
                    case h.K7.ajax:
                        t.push("xhr");
                        break;
                    case h.K7.jserrors:
                        t.push("err");
                        break;
                    case h.K7.genericEvents:
                        t.push("ins");
                        break;
                    case h.K7.sessionTrace:
                        t.push("stn");
                        break;
                    case h.K7.softNav:
                    case h.K7.spa:
                        t.push("spa")
                    }
                }
                ))
            } catch (e) {}
            return t
        }
        var l = i(5284)
          , m = i(944)
          , f = i(5942)
          , p = i(5344)
          , g = i(5181)
          , v = i(8779)
          , y = i(1863)
          , b = i(3371);
        class T {
            #o;
            #c;
            #h;
            #u = !1;
            constructor(e) {
                this.#o = (0,
                b.f)(e)?.session,
                this.processStoredDiff()
            }
            get ready() {
                return this.#u
            }
            get correctedOriginTime() {
                return this.#c
            }
            get localTimeDiff() {
                return this.#h
            }
            processRumRequest(e, t, i, s) {
                if (this.processStoredDiff(),
                this.#u)
                    return;
                if (!s)
                    throw new Error("nrServerTime not found");
                const n = t + (i - t) / 2;
                if (this.#c = Math.floor(s - n),
                this.#h = r.WN - this.#c,
                isNaN(this.#c))
                    throw new Error("Failed to correct browser time to server time");
                this.#o?.write({
                    serverTimeDiff: this.#h
                }),
                this.#u = !0
            }
            convertRelativeTimestamp(e) {
                return r.WN + e
            }
            convertAbsoluteTimestamp(e) {
                return e - r.WN
            }
            correctAbsoluteTimestamp(e) {
                return e - this.#h
            }
            correctRelativeTimestamp(e) {
                return this.correctAbsoluteTimestamp(this.convertRelativeTimestamp(e))
            }
            processStoredDiff() {
                if (this.#u)
                    return;
                const e = this.#o?.read()?.serverTimeDiff;
                "number" != typeof e || isNaN(e) || (this.#h = e,
                this.#c = r.WN - this.#h,
                this.#u = !0)
            }
        }
        var S = i(3311);
        class w extends f.r {
            static featureName = c.T;
            constructor(e) {
                if (super(e, c.T),
                this.timeToFirstByte = 0,
                this.firstByteToWindowLoad = 0,
                this.firstByteToDomContent = 0,
                this.timeKeeper = new T(e.agentIdentifier),
                !(0,
                a.fn)(e.agentIdentifier))
                    return this.ee.abort(),
                    (0,
                    m.R)(43);
                r.RI ? v.j.subscribe(( ({value: e, attrs: t}) => {
                    const i = t.navigationEntry;
                    this.timeToFirstByte = Math.max(e, this.timeToFirstByte),
                    this.firstByteToWindowLoad = Math.max(Math.round(i.loadEventEnd - this.timeToFirstByte), this.firstByteToWindowLoad),
                    this.firstByteToDomContent = Math.max(Math.round(i.domContentLoadedEventEnd - this.timeToFirstByte), this.firstByteToDomContent),
                    this.sendRum()
                }
                )) : this.sendRum()
            }
            sendRum() {
                const e = this.agentRef.info
                  , t = new o.M(this)
                  , i = {};
                e.queueTime && (i.qt = e.queueTime),
                e.applicationTime && (i.ap = e.applicationTime),
                i.be = this.timeToFirstByte,
                i.fe = this.firstByteToWindowLoad,
                i.dc = this.firstByteToDomContent;
                const a = {
                    tt: e.ttGuid,
                    us: e.user,
                    ac: e.account,
                    pr: e.product,
                    af: d(this.agentIdentifier).join(","),
                    ...i,
                    xx: e.extra,
                    ua: e.userAttributes,
                    at: e.atts
                };
                let c;
                if (this.agentRef.runtime.session && (a.fsh = Number(this.agentRef.runtime.session.isNew)),
                "object" == typeof e.jsAttributes && Object.keys(e.jsAttributes).length > 0 && (c = (0,
                S.G)({
                    ja: e.jsAttributes
                }, this.obfuscator.obfuscateString.bind(this.obfuscator), "string")),
                r.gm.performance)
                    if ("undefined" != typeof PerformanceNavigationTiming) {
                        const e = r.gm?.performance?.getEntriesByType("navigation")?.[0]
                          , t = {
                            timing: (0,
                            s.eM)(r.WN, e, {}),
                            navigation: (0,
                            s.si)(e, {})
                        };
                        a.perf = (0,
                        n.A)(t)
                    } else if ("undefined" != typeof PerformanceTiming) {
                        const e = {
                            timing: (0,
                            s.eM)(r.WN, r.gm.performance.timing, {}, !0),
                            navigation: (0,
                            s.si)(r.gm.performance.navigation, {})
                        };
                        a.perf = (0,
                        n.A)(e)
                    }
                a.fp = g.J.current.value,
                a.fcp = p.j.current.value,
                this.timeKeeper?.ready && (a.timestamp = Math.floor(this.timeKeeper.correctRelativeTimestamp((0,
                y.t)())));
                const h = (0,
                y.t)();
                t.send({
                    endpoint: "rum",
                    payload: {
                        qs: a,
                        body: c
                    },
                    opts: {
                        needResponse: !0,
                        sendEmptyBody: !0
                    },
                    cbFinished: ({status: e, responseText: t, xhr: i}) => {
                        const r = (0,
                        y.t)();
                        if (e >= 400 || 0 === e)
                            this.ee.abort();
                        else
                            try {
                                const {app: e, ...s} = JSON.parse(t);
                                try {
                                    if (this.timeKeeper.processRumRequest(i, h, r, e.nrServerTime),
                                    !this.timeKeeper.ready)
                                        throw new Error("TimeKeeper not ready");
                                    this.agentRef.runtime.timeKeeper = this.timeKeeper
                                } catch (e) {
                                    return this.ee.abort(),
                                    void (0,
                                    m.R)(17, e)
                                }
                                this.agentRef.runtime.appMetadata = e,
                                (0,
                                l.t)(s, this.agentIdentifier),
                                this.drain()
                            } catch (e) {
                                this.ee.abort(),
                                (0,
                                m.R)(18, e)
                            }
                    }
                })
            }
        }
    }
    ,
    5999: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => R
        });
        var r = i(5519)
          , s = i(1140)
          , n = i(3606)
          , a = i(9908)
          , o = i(782)
          , c = i(860)
          , h = i(5942)
          , u = i(7226)
          , d = i(1083)
          , l = i(6773)
          , m = i(6154);
        const f = new l.x(d.w.CUMULATIVE_LAYOUT_SHIFT,(e => e));
        m.RI && (0,
        u.IN)(( ({value: e, attribution: t, id: i}) => {
            const r = {
                metricId: i,
                largestShiftTarget: t.largestShiftTarget,
                largestShiftTime: t.largestShiftTime,
                largestShiftValue: t.largestShiftValue,
                loadState: t.loadState
            };
            f.update({
                value: e,
                attrs: r
            })
        }
        ), {
            reportAllChanges: !0
        });
        var p = i(5344);
        const g = new l.x(d.w.FIRST_INPUT_DELAY);
        m.RI && (0,
        u.lt)(( ({value: e, attribution: t}) => {
            if (m.mw || g.isValid)
                return;
            const i = {
                type: t.eventType,
                fid: Math.round(e),
                eventTarget: t.eventTarget,
                loadState: t.loadState
            };
            g.update({
                value: t.eventTime,
                attrs: i
            })
        }
        ));
        var v = i(5181);
        const y = new l.x(d.w.INTERACTION_TO_NEXT_PAINT);
        m.RI && (0,
        u.rH)(( ({value: e, attribution: t, id: i}) => {
            const r = {
                metricId: i,
                eventTarget: t.interactionTarget,
                eventTime: t.interactionTime,
                interactionTarget: t.interactionTarget,
                interactionTime: t.interactionTime,
                interactionType: t.interactionType,
                inputDelay: t.inputDelay,
                nextPaintTime: t.nextPaintTime,
                processingDuration: t.processingDuration,
                presentationDelay: t.presentationDelay,
                loadState: t.loadState
            };
            y.update({
                value: e,
                attrs: r
            })
        }
        ));
        var b = i(9119);
        const T = new l.x(d.w.LARGEST_CONTENTFUL_PAINT);
        m.RI && (0,
        u.fK)(( ({value: e, attribution: t}) => {
            if (m.mw || T.isValid)
                return;
            let i;
            const r = t.lcpEntry;
            r && (i = {
                size: r.size,
                eid: r.id,
                element: t.element,
                timeToFirstByte: t.timeToFirstByte,
                resourceLoadDelay: t.resourceLoadDelay,
                resourceLoadDuration: t.resourceLoadDuration,
                resourceLoadTime: t.resourceLoadDuration,
                elementRenderDelay: t.elementRenderDelay
            },
            t.url && (i.elUrl = (0,
            b.L)(t.url)),
            r.element?.tagName && (i.elTag = r.element.tagName)),
            T.update({
                value: e,
                attrs: i
            })
        }
        ));
        var S = i(8779)
          , w = i(2843);
        class R extends h.r {
            static featureName = o.T;
            #d = ({name: e, value: t, attrs: i}) => {
                this.addTiming(e, t, i)
            }
            ;
            constructor(e) {
                super(e, o.T),
                this.curSessEndRecorded = !1,
                (0,
                n.i)("docHidden", (e => this.endCurrentSession(e)), this.featureName, this.ee),
                (0,
                n.i)("winPagehide", (e => this.addTiming("unload", e, null)), this.featureName, this.ee);
                const t = e.init.page_view_timing.harvestTimeSeconds || 30;
                this.waitForFlags([]).then(( () => {
                    v.J.subscribe(this.#d),
                    p.j.subscribe(this.#d),
                    g.subscribe(this.#d),
                    T.subscribe(this.#d),
                    y.subscribe(this.#d),
                    S.j.subscribe(( ({attrs: e}) => {
                        this.addTiming("load", Math.round(e.navigationEntry.loadEventEnd))
                    }
                    )),
                    (0,
                    w.u)(( () => {
                        const {name: e, value: t, attrs: i} = f.current;
                        void 0 !== t && this.addTiming(e, 1e3 * t, i)
                    }
                    ), !0);
                    new s.n(c.$J[this.featureName],{
                        onFinished: e => this.postHarvestCleanup(e.sent && e.retry),
                        getPayload: e => this.makeHarvestPayload(e.retry)
                    },this).startTimer(t),
                    this.drain()
                }
                ))
            }
            endCurrentSession(e) {
                this.curSessEndRecorded || (this.addTiming("pageHide", e, null),
                this.curSessEndRecorded = !0)
            }
            addTiming(e, t, i) {
                (function(e) {
                    var t = navigator.connection || navigator.mozConnection || navigator.webkitConnection;
                    if (!t)
                        return;
                    t.type && (e["net-type"] = t.type);
                    t.effectiveType && (e["net-etype"] = t.effectiveType);
                    t.rtt && (e["net-rtt"] = t.rtt);
                    t.downlink && (e["net-dlink"] = t.downlink)
                }
                )(i = i || {}),
                e !== d.w.CUMULATIVE_LAYOUT_SHIFT && f.current.value >= 0 && (i.cls = f.current.value),
                this.events.add({
                    name: e,
                    value: t,
                    attrs: i
                }),
                (0,
                a.p)("pvtAdded", [e, t, i], void 0, c.K7.sessionTrace, this.ee)
            }
            appendGlobalCustomAttributes(e) {
                var t = e.attrs || {}
                  , i = ["size", "eid", "cls", "type", "fid", "elTag", "elUrl", "net-type", "net-etype", "net-rtt", "net-dlink"];
                Object.entries(this.agentRef.info.jsAttributes || {}).forEach(( ([e,r]) => {
                    i.indexOf(e) < 0 && (t[e] = r)
                }
                ))
            }
            serializer(e) {
                for (var t = (0,
                r.uJ)(this.agentIdentifier), i = "bel.6;", s = 0; s < e.length; s++) {
                    var n = e[s];
                    i += "e,",
                    i += t(n.name) + ",",
                    i += (0,
                    r.me)(n.value, r.sH, !1) + ",",
                    this.appendGlobalCustomAttributes(n);
                    var a = (0,
                    r.AQ)(n.attrs, t);
                    a && a.length > 0 && (i += (0,
                    r.sH)(a.length) + ";" + a.join(";")),
                    s + 1 < e.length && (i += ";")
                }
                return i
            }
        }
    }
    ,
    6167: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => N
        });
        var r = i(3606)
          , s = i(1140)
          , n = i(6344)
          , a = i(5942);
        let o;
        const c = new Promise((e => {
            o = e
        }
        ))
          , h = Object.freeze({
            onReplayReady: o,
            sessionReplayInitialized: c
        });
        var u = i(3762)
          , d = i(944)
          , l = i(6154)
          , m = i(3969)
          , f = i(9908)
          , p = i(860)
          , g = i(9324)
          , v = i(2614)
          , y = i(3304)
          , b = i(5851)
          , T = i(1863)
          , S = i(5270)
          , w = i(7699)
          , R = i(9119);
        class N extends a.r {
            static featureName = n.TZ;
            mode = v.g.OFF;
            constructor(e, t) {
                super(e, n.TZ),
                this.harvestTimeSeconds = e.init.session_replay.harvestTimeSeconds || 60,
                this.initialized = !1,
                this.blocked = !1,
                this.gzipper = void 0,
                this.u8 = void 0,
                this.entitled = !1,
                this.timeKeeper = void 0,
                this.recorder = t?.recorder,
                this.errorNoticed = t?.errorNoticed || !1,
                (0,
                f.p)(m.xV, ["Config/SessionReplay/Enabled"], void 0, p.K7.metrics, this.ee),
                this.ee.on(v.tS.RESET, ( () => {
                    this.abort(n.bc.RESET)
                }
                )),
                this.ee.on(v.tS.PAUSE, ( () => {
                    this.recorder?.stopRecording()
                }
                )),
                this.ee.on(v.tS.RESUME, ( () => {
                    this.recorder && (this.mode = e.runtime.session.state.sessionReplayMode,
                    this.initialized && this.mode !== v.g.OFF && this.recorder?.startRecording())
                }
                )),
                this.ee.on(v.tS.UPDATE, ( (e, t) => {
                    this.recorder && this.initialized && !this.blocked && e === v.iL.CROSS_TAB && (this.mode !== v.g.OFF && t.sessionReplayMode === v.g.OFF && this.abort(n.bc.CROSS_TAB),
                    this.mode = t.sessionReplay)
                }
                )),
                this.scheduler = new s.n(p.$J[this.featureName],{
                    onFinished: e => this.postHarvestCleanup(e),
                    retryDelay: this.harvestTimeSeconds,
                    getPayload: ({retry: e, ...t}) => this.makeHarvestPayload(e, t),
                    raw: !0
                },this),
                (0,
                r.i)(n.G4.PAUSE, ( () => {
                    this.forceStop(this.mode !== v.g.ERROR)
                }
                ), this.featureName, this.ee),
                (0,
                r.i)(n.G4.ERROR_DURING_REPLAY, (e => {
                    this.handleError(e)
                }
                ), this.featureName, this.ee);
                const {error_sampling_rate: i, sampling_rate: a, autoStart: o, block_selector: c, mask_text_selector: u, mask_all_inputs: d, inline_images: l, collect_fonts: g} = e.init.session_replay;
                this.waitForFlags(["srs", "sr"]).then(( ([e,t]) => {
                    if (this.entitled = !!t,
                    !this.entitled)
                        return this.deregisterDrain(),
                        void (this.recorder?.recording && (this.abort(n.bc.ENTITLEMENTS),
                        (0,
                        f.p)(m.xV, ["SessionReplay/EnabledNotEntitled/Detected"], void 0, p.K7.metrics, this.ee)));
                    this.drain(),
                    this.initializeRecording(e)
                }
                )).then(( () => {
                    if (this.mode === v.g.OFF)
                        for (this.recorder?.stopRecording(); this.recorder?.getEvents().events.length; )
                            this.recorder?.clearBuffer?.();
                    h.onReplayReady(this.mode)
                }
                )),
                o || (0,
                f.p)(m.xV, ["Config/SessionReplay/AutoStart/Modified"], void 0, p.K7.metrics, this.ee),
                !0 === g && (0,
                f.p)(m.xV, ["Config/SessionReplay/CollectFonts/Modified"], void 0, p.K7.metrics, this.ee),
                !0 === l && (0,
                f.p)(m.xV, ["Config/SessionReplay/InlineImages/Modifed"], void 0, p.K7.metrics, this.ee),
                !0 !== d && (0,
                f.p)(m.xV, ["Config/SessionReplay/MaskAllInputs/Modified"], void 0, p.K7.metrics, this.ee),
                "[data-nr-block]" !== c && (0,
                f.p)(m.xV, ["Config/SessionReplay/BlockSelector/Modified"], void 0, p.K7.metrics, this.ee),
                "*" !== u && (0,
                f.p)(m.xV, ["Config/SessionReplay/MaskTextSelector/Modified"], void 0, p.K7.metrics, this.ee),
                (0,
                f.p)(m.xV, ["Config/SessionReplay/SamplingRate/Value", a], void 0, p.K7.metrics, this.ee),
                (0,
                f.p)(m.xV, ["Config/SessionReplay/ErrorSamplingRate/Value", i], void 0, p.K7.metrics, this.ee)
            }
            replayIsActive() {
                return Boolean(this.scheduler?.started && this.recorder && this.mode === v.g.FULL && !this.blocked && this.entitled)
            }
            handleError(e) {
                this.recorder && (this.recorder.currentBufferTarget.hasError = !0),
                this.mode === v.g.ERROR && "visible" === l.gm?.document.visibilityState && this.switchToFull()
            }
            switchToFull() {
                this.entitled && !this.blocked && (this.mode = v.g.FULL,
                this.recorder && this.initialized ? (this.recorder.recording || this.recorder.startRecording(),
                this.scheduler.startTimer(this.harvestTimeSeconds),
                this.syncWithSessionManager({
                    sessionReplayMode: this.mode
                })) : this.initializeRecording(!1, !0, !0))
            }
            async initializeRecording(e, t) {
                if (this.initialized = !0,
                !this.entitled)
                    return;
                const {session: r, timeKeeper: s} = this.agentRef.runtime;
                if (this.timeKeeper = s,
                this.recorder?.parent.trigger === n.Qb.API && this.recorder?.recording ? this.mode = v.g.FULL : r.isNew || t ? this.mode = e : this.mode = r.state.sessionReplayMode,
                this.mode !== v.g.OFF) {
                    if (this.recorder)
                        this.recorder.parent = this;
                    else
                        try {
                            const {Recorder: e} = await Promise.all([i.e(478), i.e(249)]).then(i.bind(i, 8589));
                            this.recorder = new e(this),
                            this.recorder.currentBufferTarget.hasError = this.errorNoticed
                        } catch (e) {
                            return this.abort(n.bc.IMPORT)
                        }
                    this.mode === v.g.ERROR && this.errorNoticed && (this.mode = v.g.FULL),
                    this.mode === v.g.FULL && ("preloaded" === this.recorder?.getEvents().type && this.prepUtils().then(( () => {
                        this.scheduler.runHarvest()
                    }
                    )),
                    this.scheduler.started || this.scheduler.startTimer(this.harvestTimeSeconds)),
                    await this.prepUtils(),
                    this.recorder.recording || this.recorder.startRecording(),
                    this.syncWithSessionManager({
                        sessionReplayMode: this.mode
                    })
                }
            }
            async prepUtils() {
                try {
                    const {gzipSync: e, strToU8: t} = await i.e(212).then(i.bind(i, 9861));
                    this.gzipper = e,
                    this.u8 = t
                } catch (e) {}
            }
            makeHarvestPayload(e, t) {
                if (!this.recorder || !this.timeKeeper?.ready || !this.recorder.hasSeenSnapshot)
                    return;
                const i = this.recorder.getEvents();
                if (!i.events.length || this.mode !== v.g.FULL || this.blocked)
                    return;
                const r = this.getHarvestContents(i);
                if (!r.body.length)
                    return void this.recorder.clearBuffer();
                (0,
                f.p)(m.xV, ["SessionReplay/Harvest/Attempts"], void 0, p.K7.metrics, this.ee);
                let s = 0;
                if (this.gzipper && this.u8 ? (r.body = this.gzipper(this.u8("[".concat(r.body.map(( ({__serialized: e, ...t}) => {
                    if (t.__newrelic && e)
                        return e;
                    const i = {
                        ...t
                    };
                    return i.__newrelic || (i.__newrelic = (0,
                    S.CT)(t.timestamp, this.timeKeeper),
                    i.timestamp = this.timeKeeper.correctAbsoluteTimestamp(t.timestamp)),
                    (0,
                    y.A)(i)
                }
                )).join(","), "]"))),
                s = r.body.length,
                this.scheduler.opts.gzip = !0) : (r.body = r.body.map(( ({__serialized: e, ...t}) => {
                    if (t.__newrelic)
                        return t;
                    const i = {
                        ...t
                    };
                    return i.__newrelic = (0,
                    S.CT)(t.timestamp, this.timeKeeper),
                    i.timestamp = this.timeKeeper.correctAbsoluteTimestamp(t.timestamp),
                    i
                }
                )),
                s = (0,
                y.A)(r.body).length,
                this.scheduler.opts.gzip = !1),
                !(s > w.I))
                    return this.agentRef.runtime.session.state.sessionReplaySentFirstChunk || this.syncWithSessionManager({
                        sessionReplaySentFirstChunk: !0
                    }),
                    this.recorder.clearBuffer(),
                    "preloaded" === i.type && this.scheduler.runHarvest(t),
                    [r];
                this.abort(n.bc.TOO_BIG, s)
            }
            getCorrectedTimestamp(e) {
                if (e?.timestamp)
                    return e.__newrelic ? e.timestamp : this.timeKeeper.correctAbsoluteTimestamp(e.timestamp)
            }
            getHarvestContents(e) {
                e ??= this.recorder.getEvents();
                let t = e.events;
                const i = this.agentRef.runtime
                  , r = this.agentRef.info.jsAttributes?.["enduser.id"];
                t?.[0]?.type === n._s.FullSnapshot && this.recorder.lastMeta && (e.hasMeta = !0,
                t.unshift(this.recorder.lastMeta),
                this.recorder.lastMeta = void 0);
                t[t.length - 1]?.type === n._s.Meta && (this.recorder.lastMeta = t[t.length - 1],
                t = t.slice(0, t.length - 1),
                e.hasMeta = !!t.find((e => e.type === n._s.Meta)));
                const s = (0,
                T.t)()
                  , a = this.getCorrectedTimestamp(t[0])
                  , o = this.getCorrectedTimestamp(t[t.length - 1])
                  , c = a || Math.floor(this.timeKeeper.correctAbsoluteTimestamp(e.cycleTimestamp))
                  , h = o || Math.floor(this.timeKeeper.correctRelativeTimestamp(s))
                  , d = i.appMetadata?.agents?.[0] || {};
                return {
                    qs: {
                        browser_monitoring_key: this.agentRef.info.licenseKey,
                        type: "SessionReplay",
                        app_id: this.agentRef.info.applicationID,
                        protocol_version: "0",
                        timestamp: c,
                        attributes: (0,
                        u.WL)({
                            ...!!this.gzipper && !!this.u8 && {
                                content_encoding: "gzip"
                            },
                            ...d.entityGuid && {
                                entityGuid: d.entityGuid
                            },
                            harvestId: [i.session?.state.value, i.ptid, i.harvestCount].filter((e => e)).join("_"),
                            "replay.firstTimestamp": c,
                            "replay.lastTimestamp": h,
                            "replay.nodes": t.length,
                            "session.durationMs": i.session.getDuration(),
                            agentVersion: i.version,
                            session: i.session.state.value,
                            rst: s,
                            hasMeta: e.hasMeta || !1,
                            hasSnapshot: e.hasSnapshot || !1,
                            hasError: e.hasError || !1,
                            isFirstChunk: !1 === i.session.state.sessionReplaySentFirstChunk,
                            decompressedBytes: e.payloadBytesEstimation,
                            invalidStylesheetsDetected: b.m.invalidStylesheetsDetected,
                            inlinedAllStylesheets: e.inlinedAllStylesheets,
                            "rrweb.version": g.Yq,
                            "payload.type": e.type,
                            ...r && {
                                "enduser.id": this.obfuscator.obfuscateString(r)
                            },
                            currentUrl: this.obfuscator.obfuscateString((0,
                            R.L)("" + location))
                        }, n.BB).substring(1)
                    },
                    body: t
                }
            }
            postHarvestCleanup(e) {
                429 === e.status && this.abort(n.bc.TOO_MANY),
                this.blocked && this.scheduler.stopTimer(!0)
            }
            forceStop(e) {
                e && this.scheduler.runHarvest(),
                this.mode = v.g.OFF,
                this.recorder?.stopRecording?.(),
                this.syncWithSessionManager({
                    sessionReplayMode: this.mode
                })
            }
            abort(e={}, t) {
                for ((0,
                d.R)(33, e.message),
                (0,
                f.p)(m.xV, ["SessionReplay/Abort/".concat(e.sm), t], void 0, p.K7.metrics, this.ee),
                this.blocked = !0,
                this.mode = v.g.OFF,
                this.recorder?.stopRecording?.(),
                this.syncWithSessionManager({
                    sessionReplayMode: this.mode
                }),
                this.recorder?.clearTimestamps?.(),
                this.ee.emit("REPLAY_ABORTED"); this.recorder?.getEvents().events.length; )
                    this.recorder?.clearBuffer?.()
            }
            syncWithSessionManager(e={}) {
                this.agentRef.runtime.session.write(e)
            }
        }
    }
    ,
    5851: (e, t, i) => {
        i.d(t, {
            m: () => n
        });
        var r = i(384)
          , s = i(6154);
        const n = new class {
            #l = new WeakSet;
            #m = [];
            invalidStylesheetsDetected = !1;
            failedToFix = 0;
            evaluate() {
                let e = 0;
                if (this.#m = [],
                s.RI)
                    for (let t = 0; t < Object.keys(document.styleSheets).length; t++)
                        if (!this.#l.has(document.styleSheets[t])) {
                            this.#l.add(document.styleSheets[t]);
                            try {
                                document.styleSheets[t].cssRules
                            } catch (i) {
                                if (!document.styleSheets[t].href)
                                    return;
                                e++,
                                this.#m.push(document.styleSheets[t])
                            }
                        }
                return e && (this.invalidStylesheetsDetected = !0),
                e
            }
            async fix() {
                await Promise.all(this.#m.map((e => this.#f(e)))),
                this.#m = [];
                const e = this.failedToFix;
                return this.failedToFix = 0,
                e
            }
            async #f(e) {
                if (e?.href)
                    try {
                        const t = await (0,
                        r.dV)().o.FETCH.bind(window)(e.href);
                        if (!t.ok)
                            return void this.failedToFix++;
                        const i = await t.text();
                        try {
                            const t = new CSSStyleSheet;
                            await t.replace(i),
                            Object.defineProperty(e, "cssRules", {
                                get: () => t.cssRules
                            }),
                            Object.defineProperty(e, "rules", {
                                get: () => t.rules
                            })
                        } catch (t) {
                            Object.defineProperty(e, "cssText", {
                                get: () => i
                            }),
                            this.failedToFix++
                        }
                    } catch (e) {
                        this.failedToFix++
                    }
            }
        }
    }
    ,
    575: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => T
        });
        var r = i(3606)
          , s = i(1140)
          , n = i(3738)
          , a = i(5942)
          , o = i(6154)
          , c = i(2614)
          , h = i(1863)
          , u = i(7485);
        class d {
            constructor(e, t, i, r, s) {
                this.n = e,
                this.s = t,
                this.e = i,
                this.o = r,
                this.t = s
            }
        }
        const l = "function" == typeof o.gm.PerformanceObserver
          , m = {
            global: {
                mouseup: !0,
                mousedown: !0
            },
            window: {
                load: !0,
                pagehide: !0
            },
            xhrOriginMissing: {
                ignoreAll: !0
            }
        }
          , f = {
            typing: [1e3, 2e3],
            scrolling: [100, 1e3],
            mousing: [1e3, 2e3],
            touching: [1e3, 2e3]
        };
        class p {
            nodeCount = 0;
            trace = {};
            earliestTimeStamp = 1 / 0;
            latestTimeStamp = 0;
            prevStoredEvents = new Set;
            #p;
            constructor(e) {
                this.parent = e
            }
            storeSTN(e) {
                if (!this.parent.blocked) {
                    if (this.nodeCount >= n.jx) {
                        if (this.parent.mode !== c.g.ERROR)
                            return;
                        if (0 === this.trimSTNs(3e4))
                            return
                    }
                    this.trace[e.n] ? this.trace[e.n].push(e) : this.trace[e.n] = [e],
                    e.s < this.earliestTimeStamp && (this.earliestTimeStamp = e.s),
                    e.s > this.latestTimeStamp && (this.latestTimeStamp = e.s),
                    this.nodeCount++
                }
            }
            trimSTNs(e) {
                let t = 0;
                const i = Math.max((0,
                h.t)() - e, 0);
                return Object.keys(this.trace).forEach((e => {
                    const r = this.trace[e];
                    let s = r.findIndex((e => i <= e.e));
                    0 !== s && (s < 0 ? (s = r.length,
                    delete this.trace[e]) : r.splice(0, s),
                    this.nodeCount -= s,
                    t += s)
                }
                )),
                t
            }
            takeSTNs() {
                l || this.storeResources(o.gm.performance?.getEntriesByType?.("resource"));
                return {
                    stns: Object.entries(this.trace).flatMap(( ([e,t]) => {
                        if (!(e in f))
                            return t;
                        const i = this.smearEvtsByOrigin(e)
                          , r = t.sort(( (e, t) => e.s - t.s)).reduce(i, {});
                        return Object.values(r).flat()
                    }
                    ), this),
                    earliestTimeStamp: this.earliestTimeStamp,
                    latestTimeStamp: this.latestTimeStamp
                }
            }
            smearEvtsByOrigin(e) {
                const t = f[e][0]
                  , i = f[e][1]
                  , r = {};
                return (s, n) => {
                    let a = s[n.o];
                    a || (a = s[n.o] = []);
                    const o = r[n.o];
                    return "scrolling" !== e || function(e) {
                        const t = 4;
                        return !!(e && "number" == typeof e.e && "number" == typeof e.s && e.e - e.s < t)
                    }(n) ? o && n.s - o.s < i && o.e > n.s - t ? o.e = n.e : (r[n.o] = n,
                    a.push(n)) : (r[n.o] = null,
                    n.n = "scroll",
                    a.push(n)),
                    s
                }
            }
            processPVT(e, t, i) {
                this.storeTiming({
                    [e]: t
                }),
                function(e, t) {
                    return "fi" === e && !!t && "number" == typeof t.fid
                }(e, i) && this.storeEvent({
                    type: "fid",
                    target: "document"
                }, "document", t, t + i.fid)
            }
            storeTiming(e, t=!1) {
                if (e)
                    for (let i in e) {
                        let r = e[i];
                        const s = i.toLowerCase();
                        s.indexOf("size") >= 0 || s.indexOf("status") >= 0 || "number" == typeof r && r >= 0 && (r = Math.round(r),
                        this.parent.timeKeeper && this.parent.timeKeeper.ready && t && (r = this.parent.timeKeeper.convertAbsoluteTimestamp(Math.floor(this.parent.timeKeeper.correctAbsoluteTimestamp(r)))),
                        this.storeSTN(new d(i,r,r,"document","timing")))
                    }
            }
            storeEvent(e, t, i, r) {
                if (this.shouldIgnoreEvent(e, t))
                    return;
                if (this.prevStoredEvents.has(e))
                    return;
                this.prevStoredEvents.add(e);
                const s = new d(this.evtName(e.type),i,r,void 0,"event");
                try {
                    s.o = this.evtOrigin(e.target, t)
                } catch (e) {
                    s.o = this.evtOrigin(null, t)
                }
                this.storeSTN(s)
            }
            shouldIgnoreEvent(e, t) {
                const i = this.evtOrigin(e.target, t);
                return e.type in m.global || (!(!m[i] || !m[i].ignoreAll) || !(!m[i] || !(e.type in m[i])))
            }
            evtName(e) {
                switch (e) {
                case "keydown":
                case "keyup":
                case "keypress":
                    return "typing";
                case "mousemove":
                case "mouseenter":
                case "mouseleave":
                case "mouseover":
                case "mouseout":
                    return "mousing";
                case "scroll":
                    return "scrolling";
                case "touchstart":
                case "touchmove":
                case "touchend":
                case "touchcancel":
                case "touchenter":
                case "touchleave":
                    return "touching";
                default:
                    return e
                }
            }
            evtOrigin(e, t) {
                let i = "unknown";
                if (e && e instanceof XMLHttpRequest) {
                    const t = this.parent.ee.context(e).params;
                    if (!(t && t.status && t.method && t.host && t.pathname))
                        return "xhrOriginMissing";
                    i = t.status + " " + t.method + ": " + t.host + t.pathname
                } else if (e && "string" == typeof e.tagName && (i = e.tagName.toLowerCase(),
                e.id && (i += "#" + e.id),
                e.className))
                    for (let t = 0; t < e.classList.length; t++)
                        i += "." + e.classList[t];
                return "unknown" === i && ("string" == typeof t ? i = t : t === document ? i = "document" : t === window ? i = "window" : t instanceof FileReader && (i = "FileReader")),
                i
            }
            storeHist(e, t, i) {
                this.storeSTN(new d("history.pushState",i,i,e,t))
            }
            #g = 0;
            storeResources(e) {
                e && 0 !== e.length && (e.forEach((e => {
                    if ((0 | e.fetchStart) <= this.#g)
                        return;
                    const {initiatorType: t, fetchStart: i, responseEnd: r, entryType: s} = e
                      , {protocol: n, hostname: a, port: o, pathname: c} = (0,
                    u.D)(e.name)
                      , h = new d(t,0 | i,0 | r,"".concat(n, "://").concat(a, ":").concat(o).concat(c),s);
                    this.storeSTN(h)
                }
                )),
                this.#g = 0 | e[e.length - 1].fetchStart)
            }
            storeErrorAgg(e, t, i, r) {
                "err" === e && this.storeSTN(new d("error",r.time,r.time,i.message,i.stackHash))
            }
            storeXhrAgg(e, t, i, r) {
                "xhr" === e && this.storeSTN(new d("Ajax",r.time,r.time + r.duration,"".concat(i.status, " ").concat(i.method, ": ").concat(i.host).concat(i.pathname),"ajax"))
            }
            isEmpty() {
                return 0 === this.nodeCount
            }
            save() {
                this.#p = this.trace
            }
            get = this.takeSTNs;
            clear() {
                this.trace = {},
                this.nodeCount = 0,
                this.prevStoredEvents.clear(),
                this.earliestTimeStamp = 1 / 0,
                this.latestTimeStamp = 0
            }
            reloadSave() {
                Object.values(this.#p).forEach((e => e.forEach((e => this.storeSTN(e)))))
            }
            clearSave() {
                this.#p = void 0
            }
        }
        var g = i(3762)
          , v = i(3311)
          , y = i(860)
          , b = i(9119);
        class T extends a.r {
            static featureName = n.TZ;
            constructor(e) {
                super(e, n.TZ),
                this.harvestTimeSeconds = e.init.session_trace.harvestTimeSeconds || 30,
                this.entitled = void 0,
                this.everHarvested = !1,
                this.harvesting = !1,
                this.events = new p(this),
                this.waitForFlags(["sts", "st"]).then(( ([e,t]) => this.initialize(e, t)))
            }
            initialize(e, t, i) {
                return this.entitled ??= t,
                this.blocked || !this.entitled ? this.deregisterDrain() : (this.initialized || (this.initialized = !0,
                this.ptid = this.agentRef.runtime.ptid,
                this.sessionId = this.agentRef.runtime.session?.state.value,
                this.ee.on(c.tS.RESET, ( () => {
                    this.blocked || this.abort(1)
                }
                )),
                this.ee.on(c.tS.UPDATE, ( (e, t) => {
                    this.blocked || (this.mode === c.g.FULL || t.sessionReplayMode !== c.g.FULL && t.sessionTraceMode !== c.g.FULL || this.switchToFull(),
                    (this.sessionId !== t.value || "cross-tab" === e && this.scheduler?.started && t.sessionTraceMode === c.g.OFF) && this.abort(2))
                }
                )),
                "undefined" != typeof PerformanceNavigationTiming ? this.events.storeTiming(o.gm.performance?.getEntriesByType?.("navigation")[0]) : this.events.storeTiming(o.gm.performance?.timing, !0)),
                this.agentRef.runtime.session.isNew || i ? this.mode = e : this.mode = this.agentRef.runtime.session.state.sessionTraceMode,
                this.mode === c.g.OFF ? this.deregisterDrain() : (this.timeKeeper ??= this.agentRef.runtime.timeKeeper,
                this.scheduler = new s.n(y.$J[this.featureName],{
                    onFinished: e => this.postHarvestCleanup(e.sent && e.retry),
                    retryDelay: this.harvestTimeSeconds,
                    getPayload: e => this.makeHarvestPayload(e.retry),
                    raw: !0
                },this),
                (0,
                r.i)("bst", ( (...e) => this.events.storeEvent(...e)), this.featureName, this.ee),
                (0,
                r.i)("bstResource", ( (...e) => this.events.storeResources(...e)), this.featureName, this.ee),
                (0,
                r.i)("bstHist", ( (...e) => this.events.storeHist(...e)), this.featureName, this.ee),
                (0,
                r.i)("bstXhrAgg", ( (...e) => this.events.storeXhrAgg(...e)), this.featureName, this.ee),
                (0,
                r.i)("bstApi", ( (...e) => this.events.storeSTN(...e)), this.featureName, this.ee),
                (0,
                r.i)("trace-jserror", ( (...e) => this.events.storeErrorAgg(...e)), this.featureName, this.ee),
                (0,
                r.i)("pvtAdded", ( (...e) => this.events.processPVT(...e)), this.featureName, this.ee),
                this.mode === c.g.FULL ? this.startHarvesting() : (0,
                r.i)("trace-jserror", ( () => {
                    this.mode === c.g.ERROR && this.switchToFull()
                }
                ), this.featureName, this.ee),
                this.agentRef.runtime.session.write({
                    sessionTraceMode: this.mode
                }),
                void this.drain()))
            }
            startHarvesting() {
                this.scheduler.started || this.blocked || (this.scheduler.runHarvest(),
                this.scheduler.startTimer(this.harvestTimeSeconds))
            }
            preHarvestChecks() {
                if (this.mode === c.g.FULL && this.timeKeeper?.ready && this.agentRef.runtime.session) {
                    if (this.sessionId === this.agentRef.runtime.session.state.value && this.ptid === this.agentRef.runtime.ptid)
                        return !0;
                    this.abort(3)
                }
            }
            serializer({stns: e}) {
                if (e.length)
                    return this.everHarvested = !0,
                    (0,
                    v.G)(e, this.obfuscator.obfuscateString.bind(this.obfuscator), "string")
            }
            queryStringsBuilder({stns: e, earliestTimeStamp: t, latestTimeStamp: i}) {
                const r = !this.agentRef.runtime.session.state.traceHarvestStarted;
                r && this.agentRef.runtime.session.write({
                    traceHarvestStarted: !0
                });
                const s = 1 === this.agentRef.runtime.session.state.sessionReplayMode
                  , n = this.agentRef.info.jsAttributes["enduser.id"]
                  , a = this.agentRef.runtime.appMetadata.agents?.[0]?.entityGuid;
                return {
                    browser_monitoring_key: this.agentRef.info.licenseKey,
                    type: "BrowserSessionChunk",
                    app_id: this.agentRef.info.applicationID,
                    protocol_version: "0",
                    timestamp: Math.floor(this.timeKeeper.correctRelativeTimestamp(t)),
                    attributes: (0,
                    g.WL)({
                        ...a && {
                            entityGuid: a
                        },
                        harvestId: "".concat(this.agentRef.runtime.session.state.value, "_").concat(this.agentRef.runtime.ptid, "_").concat(this.agentRef.runtime.harvestCount),
                        "trace.firstTimestamp": Math.floor(this.timeKeeper.correctRelativeTimestamp(t)),
                        "trace.lastTimestamp": Math.floor(this.timeKeeper.correctRelativeTimestamp(i)),
                        "trace.nodes": e.length,
                        "trace.originTimestamp": this.timeKeeper.correctedOriginTime,
                        agentVersion: this.agentRef.runtime.version,
                        ...r && {
                            firstSessionHarvest: r
                        },
                        ...s && {
                            hasReplay: s
                        },
                        ptid: "".concat(this.ptid),
                        session: "".concat(this.sessionId),
                        ...n && {
                            "enduser.id": this.obfuscator.obfuscateString(n)
                        },
                        currentUrl: this.obfuscator.obfuscateString((0,
                        b.L)("" + location))
                    }, 5e3).substring(1)
                }
            }
            switchToFull() {
                if (this.mode === c.g.FULL || !this.entitled || this.blocked)
                    return;
                const e = this.mode;
                if (this.mode = c.g.FULL,
                this.agentRef.runtime.session.write({
                    sessionTraceMode: this.mode
                }),
                e === c.g.OFF || !this.initialized)
                    return this.initialize(this.mode, this.entitled);
                this.initialized && this.events.trimSTNs(3e4),
                this.startHarvesting()
            }
            abort() {
                this.blocked = !0,
                this.mode = c.g.OFF,
                this.agentRef.runtime.session.write({
                    sessionTraceMode: this.mode
                }),
                this.scheduler?.stopTimer(),
                this.events.clear()
            }
        }
    }
    ,
    4393: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => I
        });
        var r = i(9908)
          , s = i(3606)
          , n = i(1140)
          , a = i(6389)
          , o = i(8779)
          , c = i(860)
          , h = i(3969)
          , u = i(5942)
          , d = i(3962)
          , l = i(5519);
        let m = 0;
        class f {
            belType;
            children = [];
            start;
            end;
            callbackEnd = 0;
            callbackDuration = 0;
            nodeId = ++m;
            constructor(e) {
                if (!e)
                    throw new Error("Interaction is missing core attributes");
                this.agentIdentifier = e
            }
            addChild(e) {
                this.children.push(e)
            }
            serialize() {}
        }
        class p extends f {
            constructor(e, t) {
                super(e),
                this.belType = d.Qu.AJAX,
                this.method = t.method,
                this.status = t.status,
                this.domain = t.domain,
                this.path = t.path,
                this.txSize = t.requestSize,
                this.rxSize = t.responseSize,
                this.requestedWith = "fetch" === t.type ? 1 : "",
                this.spanId = t.spanId,
                this.traceId = t.traceId,
                this.spanTimestamp = t.spanTimestamp,
                this.gql = t.gql,
                this.start = t.startTime,
                this.end = t.endTime
            }
            serialize(e) {
                const t = (0,
                l.uJ)(this.agentIdentifier)
                  , i = []
                  , r = [(0,
                l.sH)(this.belType), 0, (0,
                l.sH)(this.start - e), (0,
                l.sH)(this.end - this.start), (0,
                l.sH)(this.callbackEnd), (0,
                l.sH)(this.callbackDuration), t(this.method), (0,
                l.sH)(this.status), t(this.domain), t(this.path), (0,
                l.sH)(this.txSize), (0,
                l.sH)(this.rxSize), this.requestedWith, t(this.nodeId), (0,
                l.me)(this.spanId, t, !0) + (0,
                l.me)(this.traceId, t, !0) + (0,
                l.me)(this.spanTimestamp, l.sH)];
                let s = [];
                return "object" == typeof this.gql && (s = (0,
                l.AQ)(this.gql, t)),
                this.children.forEach((e => s.push(e.serialize()))),
                r[1] = (0,
                l.sH)(s.length),
                i.push(r),
                s.length && i.push(s.join(";")),
                i.join(";")
            }
        }
        var g = i(2733)
          , v = i(2555)
          , y = i(6154)
          , b = i(9566)
          , T = i(1863)
          , S = i(9119);
        class w extends f {
            id = (0,
            b.bz)();
            initialPageURL = y.m;
            oldURL = "" + y.gm?.location;
            newURL = "" + y.gm?.location;
            customName;
            customAttributes = {};
            customDataByApi = {};
            queueTime;
            appTime;
            newRoute;
            status = d.ih.IP;
            domTimestamp = 0;
            historyTimestamp = 0;
            createdByApi = !1;
            keepOpenUntilEndApi = !1;
            onDone = [];
            cancellationTimer;
            constructor(e, t, i, r) {
                super(e),
                this.belType = d.Qu.INTERACTION,
                this.trigger = t,
                this.start = i,
                this.oldRoute = r,
                this.eventSubscription = new Map([["finished", []], ["cancelled", []]]),
                this.forceSave = this.forceIgnore = !1,
                this.trigger === d.AM && (this.createdByApi = !0)
            }
            updateDom(e) {
                this.domTimestamp = e || (0,
                T.t)()
            }
            updateHistory(e, t) {
                this.newURL = t || "" + y.gm?.location,
                this.historyTimestamp = e || (0,
                T.t)()
            }
            seenHistoryAndDomChange() {
                return this.historyTimestamp > 0 && this.domTimestamp > this.historyTimestamp
            }
            on(e, t) {
                if (!this.eventSubscription.has(e))
                    throw new Error("Cannot subscribe to non pre-defined events.");
                if ("function" != typeof t)
                    throw new Error("Must supply function as callback.");
                this.eventSubscription.get(e).push(t)
            }
            done(e) {
                return (!this.keepOpenUntilEndApi || void 0 !== e) && (this.onDone.forEach((e => e(this.customDataByApi))),
                this.forceIgnore ? this.#v() : this.seenHistoryAndDomChange() ? this.#y(e) : this.forceSave ? this.#y(e || performance.now()) : this.#v(),
                !0)
            }
            #y(e=0) {
                if (this.status !== d.ih.IP)
                    return;
                clearTimeout(this.cancellationTimer),
                this.end = Math.max(this.domTimestamp, this.historyTimestamp, e),
                this.customAttributes = {
                    ...(0,
                    v.Vp)(this.agentIdentifier).jsAttributes,
                    ...this.customAttributes
                },
                this.status = d.ih.FIN;
                this.eventSubscription.get("finished").forEach((e => e()))
            }
            #v() {
                if (this.status !== d.ih.IP)
                    return;
                clearTimeout(this.cancellationTimer),
                this.status = d.ih.CAN;
                this.eventSubscription.get("cancelled").forEach((e => e()))
            }
            isActiveDuring(e) {
                return this.status === d.ih.IP ? this.start <= e : this.status === d.ih.FIN && this.start <= e && this.end >= e
            }
            get firstPaint() {}
            get firstContentfulPaint() {}
            get navTiming() {}
            serialize(e) {
                const t = (0,
                l.uJ)(this.agentIdentifier)
                  , i = [];
                let r;
                r = "initialPageLoad" === this.trigger ? d.O2.INITIAL_PAGE_LOAD : this.newURL !== this.oldURL ? d.O2.ROUTE_CHANGE : d.O2.UNSPECIFIED;
                const s = [(0,
                l.sH)(this.belType), 0, (0,
                l.sH)(this.start - e), (0,
                l.sH)(this.end - this.start), (0,
                l.sH)(this.callbackEnd), (0,
                l.sH)(this.callbackDuration), t(this.trigger), t((0,
                S.L)(this.initialPageURL, !0)), t((0,
                S.L)(this.oldURL, !0)), t((0,
                S.L)(this.newURL, !0)), t(this.customName), r, (0,
                l.me)(this.queueTime, l.sH, !0) + (0,
                l.me)(this.appTime, l.sH, !0) + (0,
                l.me)(this.oldRoute, t, !0) + (0,
                l.me)(this.newRoute, t, !0) + t(this.id), t(this.nodeId), (0,
                l.me)(this.firstPaint, l.sH, !0) + (0,
                l.me)(this.firstContentfulPaint, l.sH)]
                  , n = (0,
                l.AQ)(this.customAttributes || {}, t);
                return (0,
                v.Vp)(this.agentIdentifier).atts && n.push("a," + t((0,
                v.Vp)(this.agentIdentifier).atts)),
                this.children.forEach((t => n.push(t.serialize(e || this.start)))),
                s[1] = (0,
                l.sH)(n.length),
                i.push(s),
                n.length && i.push(n.join(";")),
                this.navTiming ? i.push(this.navTiming) : i.push(""),
                i.join(";")
            }
        }
        var R = i(5181)
          , N = i(5344);
        class E extends w {
            constructor(e) {
                super(e, "initialPageLoad", 0, null);
                const t = (0,
                v.Vp)(e);
                this.queueTime = t.queueTime,
                this.appTime = t.applicationTime
            }
            get firstPaint() {
                return R.J.current.value
            }
            get firstContentfulPaint() {
                return N.j.current.value
            }
            get navTiming() {
                if (!g.ss.length)
                    return;
                let e = ","
                  , t = "b"
                  , i = 0;
                return g.ss.slice(1, 21).forEach((r => {
                    void 0 !== r ? (t += e + (0,
                    l.sH)(r - i),
                    e = ",",
                    i = r) : (t += e + "!",
                    e = "")
                }
                )),
                t
            }
        }
        class I extends u.r {
            static featureName = d.TZ;
            constructor(e, {domObserver: t}) {
                super(e, d.TZ);
                const i = e.init.soft_navigations.harvestTimeSeconds || 10;
                this.interactionsToHarvest = this.events,
                this.domObserver = t,
                this.initialPageLoadInteraction = new E(e.agentIdentifier),
                o.j.subscribe(( ({attrs: e}) => {
                    const t = e.navigationEntry.loadEventEnd;
                    this.initialPageLoadInteraction.forceSave = !0,
                    this.initialPageLoadInteraction.done(t),
                    this.interactionsToHarvest.add(this.initialPageLoadInteraction),
                    this.initialPageLoadInteraction = null,
                    (0,
                    r.p)(h.xV, ["SoftNav/Interaction/InitialPageLoad/Duration/Ms", Math.round(t)], void 0, c.K7.metrics, this.ee)
                }
                )),
                this.latestRouteSetByApi = null,
                this.interactionInProgress = null,
                this.blocked = !1,
                this.waitForFlags(["spa"]).then(( ([e]) => {
                    if (e) {
                        this.drain();
                        new n.n(c.$J[this.featureName],{
                            onFinished: e => this.postHarvestCleanup(e.sent && e.retry),
                            getPayload: e => this.makeHarvestPayload(e.retry),
                            retryDelay: i,
                            onUnload: () => this.interactionInProgress?.done()
                        },this).startTimer(i, 0)
                    } else
                        this.blocked = !0,
                        this.deregisterDrain()
                }
                )),
                (0,
                s.i)("newUIEvent", (e => this.startUIInteraction(e.type, Math.floor(e.timeStamp), e.target)), this.featureName, this.ee),
                (0,
                s.i)("newURL", ( (e, t) => this.interactionInProgress?.updateHistory(e, t)), this.featureName, this.ee),
                (0,
                s.i)("newDom", (e => {
                    this.interactionInProgress?.updateDom(e),
                    this.interactionInProgress?.seenHistoryAndDomChange() && this.interactionInProgress.done()
                }
                ), this.featureName, this.ee),
                this.#b(),
                (0,
                s.i)("ajax", this.#T.bind(this), this.featureName, this.ee),
                (0,
                s.i)("jserror", this.#S.bind(this), this.featureName, this.ee)
            }
            serializer(e) {
                let t = 0;
                const i = [];
                for (const r of e)
                    i.push(r.serialize(t)),
                    t || (t = Math.floor(r.start));
                return "bel.7;".concat(i.join(";"))
            }
            startUIInteraction(e, t, i) {
                if (!this.interactionInProgress?.createdByApi && !1 !== this.interactionInProgress?.done()) {
                    if (this.interactionInProgress = new w(this.agentIdentifier,e,t,this.latestRouteSetByApi),
                    "click" === e) {
                        const e = function(e) {
                            const t = e.tagName.toLowerCase();
                            if (["a", "button", "input"].includes(t))
                                return e.title || e.value || e.innerText
                        }(i);
                        e && (this.interactionInProgress.customAttributes.actionText = e)
                    }
                    this.interactionInProgress.cancellationTimer = setTimeout(( () => {
                        this.interactionInProgress.done(),
                        (0,
                        r.p)(h.xV, ["SoftNav/Interaction/TimeOut"], void 0, c.K7.metrics, this.ee)
                    }
                    ), 3e4),
                    this.setClosureHandlers()
                }
            }
            setClosureHandlers() {
                this.interactionInProgress.on("finished", ( () => {
                    const e = this.interactionInProgress;
                    this.interactionsToHarvest.add(this.interactionInProgress),
                    this.interactionInProgress = null,
                    this.domObserver.disconnect(),
                    (0,
                    r.p)(h.xV, ["SoftNav/Interaction/".concat(e.newURL !== e.oldURL ? "RouteChange" : "Custom", "/Duration/Ms"), Math.round(e.end - e.start)], void 0, c.K7.metrics, this.ee)
                }
                )),
                this.interactionInProgress.on("cancelled", ( () => {
                    this.interactionInProgress = null,
                    this.domObserver.disconnect()
                }
                ))
            }
            getInteractionFor(e) {
                if (this.interactionInProgress?.isActiveDuring(e))
                    return this.interactionInProgress;
                let t;
                const i = this.interactionsToHarvest.get();
                for (let r = i.length - 1; r >= 0; r--) {
                    const s = i[r];
                    if (s.isActiveDuring(e)) {
                        if ("initialPageLoad" !== s.trigger)
                            return s;
                        t = s
                    }
                }
                return t || (this.initialPageLoadInteraction?.isActiveDuring(e) ? this.initialPageLoadInteraction : void 0)
            }
            #T(e) {
                const t = this.getInteractionFor(e.startTime);
                function i(e, t, i) {
                    const r = new p(e,t);
                    i.addChild(r)
                }
                t ? t.status === d.ih.FIN ? i(this.agentIdentifier, e, t) : (t.on("finished", ( () => i(this.agentIdentifier, e, t))),
                t.on("cancelled", ( () => (0,
                r.p)("returnAjax", [e], void 0, c.K7.ajax, this.ee)))) : (0,
                r.p)("returnAjax", [e], void 0, c.K7.ajax, this.ee)
            }
            #S(e, t) {
                const i = this.getInteractionFor(t);
                i && (e.browserInteractionId = i.id,
                i.status === d.ih.FIN ? (e._softNavFinished = !0,
                e._softNavAttributes = i.customAttributes) : (i.on("finished", (0,
                a.J)(( () => (0,
                r.p)("softNavFlush", [i.id, !0, i.customAttributes], void 0, c.K7.jserrors, this.ee)))),
                i.on("cancelled", (0,
                a.J)(( () => (0,
                r.p)("softNavFlush", [i.id, !1, void 0], void 0, c.K7.jserrors, this.ee))))))
            }
            #b() {
                const e = "api-ixn-"
                  , t = this;
                (0,
                s.i)(e + "get", (function(e, {waitForEnd: i}={}) {
                    this.associatedInteraction = t.getInteractionFor(e),
                    this.associatedInteraction || (this.associatedInteraction = t.interactionInProgress = new w(t.agentIdentifier,d.AM,e,t.latestRouteSetByApi),
                    t.setClosureHandlers()),
                    !0 === i && (this.associatedInteraction.keepOpenUntilEndApi = !0)
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "end", (function(e) {
                    this.associatedInteraction.done(e)
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "save", (function() {
                    this.associatedInteraction.forceSave = !0
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "ignore", (function() {
                    this.associatedInteraction.forceIgnore = !0
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "getContext", (function(e, t) {
                    "function" == typeof t && setTimeout(( () => t(this.associatedInteraction.customDataByApi)), 0)
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "onEnd", (function(e, t) {
                    "function" == typeof t && this.associatedInteraction.onDone.push(t)
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "actionText", (function(e, t) {
                    t && (this.associatedInteraction.customAttributes.actionText = t)
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "setName", (function(e, t, i) {
                    t && (this.associatedInteraction.customName = t),
                    i && (this.associatedInteraction.trigger = i)
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "setAttribute", (function(e, t, i) {
                    this.associatedInteraction.customAttributes[t] = i
                }
                ), t.featureName, t.ee),
                (0,
                s.i)(e + "routeName", (function(e, i) {
                    t.latestRouteSetByApi = i,
                    t.interactionInProgress && (t.interactionInProgress.newRoute = i)
                }
                ), t.featureName, t.ee)
            }
        }
    }
    ,
    5592: (e, t, i) => {
        i.r(t),
        i.d(t, {
            Aggregate: () => Q
        });
        var r = i(3606)
          , s = i(7485)
          , n = i(7295)
          , a = i(2733)
          , o = i(9566)
          , c = i(2555)
          , h = i(6154)
          , u = i(384)
          , d = i(7836)
          , l = 0;
        function m(e, t, i, r) {
            Object.defineProperty(this, "interaction", {
                value: e,
                writable: !0
            }),
            this.parent = t,
            this.id = ++l,
            this.type = i,
            this.children = [],
            this.end = null,
            this.jsEnd = this.start = r,
            this.jsTime = 0,
            this.attrs = {},
            this.cancelled = !1
        }
        var f = m.prototype;
        f.child = function(e, t, i, r) {
            var s = this.interaction;
            if (s.end || s.nodes >= 128)
                return null;
            s.onNodeAdded(this);
            var n = new m(s,this,e,t);
            return n.attrs.name = i,
            s.nodes++,
            r || s.remaining++,
            n
        }
        ,
        f.callback = function(e, t) {
            var i = this;
            i.jsTime += e,
            t > i.jsEnd && (i.jsEnd = t,
            i.interaction.lastCb = t)
        }
        ,
        f.cancel = function() {
            this.cancelled = !0,
            this.interaction.remaining--
        }
        ,
        f.finish = function(e) {
            var t = this;
            if (t.end)
                return;
            t.end = e;
            let i = t.parent;
            for (; i?.cancelled; )
                i = i.parent;
            i && i.children.push(t),
            t.parent = null;
            var r = this.interaction;
            r.remaining--,
            r.lastFinish = e,
            r.checkFinish()
        }
        ;
        var p = (0,
        u.dV)().o.ST
          , g = (0,
        u.dV)().o.CT
          , v = {};
        function y(e, t, i, r, s, n) {
            this.agentIdentifier = n,
            this.ee = d.ee.get(n),
            v[n] = 0,
            this.id = ++v[n],
            this.eventName = e,
            this.nodes = 0,
            this.remaining = 0,
            this.finishTimer = null,
            this.checkingFinish = !1,
            this.lastCb = this.lastFinish = t,
            this.handlers = [],
            this.onFinished = s,
            this.done = !1;
            var a = (this.root = new m(this,null,"interaction",t)).attrs;
            a.trigger = e,
            a.initialPageURL = h.m,
            a.oldRoute = r,
            a.newURL = a.oldURL = i,
            a.custom = {},
            a.store = {}
        }
        var b = y.prototype;
        b.checkFinish = function() {
            var e = this;
            e.remaining > 0 ? e._resetFinishCheck() : e.checkingFinish || null === e.root.end && (e._resetFinishCheck(),
            e.checkingFinish = !0,
            e.finishTimer = p(( () => {
                e.checkingFinish = !1,
                e.finishTimer = p(( () => {
                    e.finishTimer = null,
                    e.remaining <= 0 && e.finish()
                }
                ), 1)
            }
            ), 0))
        }
        ,
        b.setNewURL = function(e) {
            this.root.attrs.newURL = e
        }
        ,
        b.setNewRoute = function(e) {
            this.root.attrs.newRoute = e
        }
        ,
        b.onNodeAdded = function() {
            this._resetFinishCheck()
        }
        ,
        b._resetFinishCheck = function() {
            this.finishTimer && (g(this.finishTimer),
            this.finishTimer = null,
            this.checkingFinish = !1)
        }
        ,
        b.finish = function() {
            var e = this
              , t = e.root;
            if (null === t.end) {
                var i = Math.max(e.lastCb, e.lastFinish)
                  , r = t.attrs.custom;
                this.onFinished && this.onFinished(this),
                Object.entries((0,
                c.Vp)(e.agentIdentifier).jsAttributes || {}).forEach(( ([e,t]) => {
                    e in r || (r[e] = t)
                }
                )),
                t.end = i,
                e.ee.emit("interaction", [this])
            }
        }
        ;
        var T = i(3878)
          , S = i(1140)
          , w = i(9119)
          , R = i(5519)
          , N = i(4777);
        class E extends N.J {
            constructor(e) {
                super(e),
                this.firstTimestamp = void 0
            }
            serializeMultiple(e, t, i) {
                const r = (0,
                c.Vp)(this.sharedContext.agentIdentifier);
                var s = (0,
                R.uJ)(this.sharedContext.agentIdentifier)
                  , n = "bel.7";
                return e.forEach((e => {
                    n += ";" + this.serializeInteraction(e.root, t, i, e.routeChange, s, r)
                }
                )),
                this.firstTimestamp = void 0,
                n
            }
            serializeSingle(e, t, i, r) {
                const s = (0,
                c.Vp)(this.sharedContext.agentIdentifier);
                var n = (0,
                R.uJ)(this.sharedContext.agentIdentifier)
                  , a = "bel.7;" + this.serializeInteraction(e, t, i, r, n, s);
                return this.firstTimestamp = void 0,
                a
            }
            serializeInteraction(e, t, i, r, s, n) {
                t = t || 0;
                var a = "initialPageLoad" === e.attrs.trigger
                  , o = {
                    interaction: 1,
                    ajax: 2,
                    customTracer: 4
                }
                  , c = !0;
                const h = (e, u) => {
                    if ("customEnd" === e.type)
                        return u.push([3, (0,
                        R.sH)(e.end - this.firstTimestamp)]);
                    var d = e.type
                      , l = o[d]
                      , m = e.start
                      , f = e.children.length
                      , p = 0
                      , g = n.atts
                      , v = a && i.length && 1 === l
                      , y = []
                      , b = e.attrs
                      , T = b.metrics
                      , S = b.params
                      , N = n.queueTime
                      , E = n.applicationTime;
                    void 0 === this.firstTimestamp ? (m += t,
                    this.firstTimestamp = m) : m -= this.firstTimestamp;
                    var I = [(0,
                    R.sH)(m), (0,
                    R.sH)(e.end - e.start), (0,
                    R.sH)(e.jsEnd - e.end), (0,
                    R.sH)(e.jsTime)];
                    switch (l) {
                    case 1:
                        I[2] = (0,
                        R.sH)(e.jsEnd - this.firstTimestamp),
                        I.push(s(b.trigger), s((0,
                        w.L)(b.initialPageURL, c)), s((0,
                        w.L)(b.oldURL, c)), s((0,
                        w.L)(b.newURL, c)), s(b.customName), a ? "" : r ? 1 : 2, (0,
                        R.me)(a && N, R.sH, !0) + (0,
                        R.me)(a && E, R.sH, !0) + (0,
                        R.me)(b.oldRoute, s, !0) + (0,
                        R.me)(b.newRoute, s, !0) + s(b.id), s(e.id), (0,
                        R.me)(b.firstPaint, R.sH, !0) + (0,
                        R.me)(b.firstContentfulPaint, R.sH, !1));
                        var A = (0,
                        R.AQ)(b.custom, s);
                        y = y.concat(A),
                        p = A.length,
                        g && (f++,
                        y.push("a," + s(g)));
                        break;
                    case 2:
                        if (I.push(s(S.method), (0,
                        R.sH)(S.status), s(S.host), s(S.pathname), (0,
                        R.sH)(T.txSize), (0,
                        R.sH)(T.rxSize), b.isFetch ? 1 : b.isJSONP ? 2 : "", s(e.id), (0,
                        R.me)(e.dt && e.dt.spanId, s, !0) + (0,
                        R.me)(e.dt && e.dt.traceId, s, !0) + (0,
                        R.me)(e.dt && e.dt.timestamp, R.sH, !1)),
                        Object.keys(S?.gql || {}).length) {
                            var x = (0,
                            R.AQ)(S.gql, s);
                            y = y.concat(x),
                            p = x.length
                        }
                        break;
                    case 4:
                        var k = b.tracedTime;
                        I.push(s(b.name), (0,
                        R.me)(k, R.sH, !0) + s(e.id))
                    }
                    for (var M = 0; M < e.children.length; M++)
                        h(e.children[M], y);
                    if (I.unshift((0,
                    R.sH)(l), (0,
                    R.sH)(f += p)),
                    u.push(I),
                    f && u.push(y.join(";")),
                    v) {
                        var C = ","
                          , F = "b"
                          , O = 0;
                        Object.values(i.slice(1, 21) || {}).forEach((e => {
                            void 0 !== e ? (F += C + (0,
                            R.sH)(e - O),
                            C = ",",
                            O = e) : (F += C + "!",
                            C = "")
                        }
                        )),
                        u.push(F)
                    } else
                        1 === l && u.push("");
                    return u
                }
                ;
                return h(e, []).join(";")
            }
        }
        var I = i(7378)
          , A = i(860)
          , x = i(5942)
          , k = i(5344)
          , M = i(5181)
          , C = i(5607)
          , F = i(9908)
          , O = i(3969)
          , j = i(944);
        const {TZ: P, NC: L, xq: D, uP: H, Lc: _, rw: B, SG: U, l9: K, dT: z, oW: V, U6: q, op: G, UT: J, gx: W, BR: Z, L3: X} = I;
        class Q extends x.r {
            static featureName = P;
            constructor(e) {
                super(e, P);
                const t = this.state = {
                    initialPageURL: h.m,
                    lastSeenUrl: h.m,
                    lastSeenRouteName: null,
                    timerMap: {},
                    timerBudget: D,
                    currentNode: null,
                    prevNode: null,
                    nodeOnLastHashUpdate: null,
                    initialPageLoad: null,
                    pageLoaded: !1,
                    childTime: 0,
                    depth: 0,
                    harvestTimeSeconds: e.init.spa.harvestTimeSeconds || 10,
                    disableSpaFix: (e.init.feature_flags || []).indexOf("disable-spa-fix") > -1
                };
                this.spaSerializerClass = new E(this);
                const i = this;
                let a;
                const c = d.ee.get(e.agentIdentifier)
                  , u = c.get("mutation")
                  , l = c.get("promise")
                  , m = c.get("history")
                  , f = c.get("events")
                  , p = c.get("timer")
                  , g = c.get("fetch")
                  , v = c.get("jsonp")
                  , b = c.get("xhr")
                  , w = c.get("tracer");
                if (this.waitForFlags(["spa"]).then(( ([e]) => {
                    e ? (a = new S.n(A.$J[this.featureName],{
                        onFinished: e => this.postHarvestCleanup(e.sent && e.retry),
                        getPayload: e => this.makeHarvestPayload(e.retry),
                        retryDelay: t.harvestTimeSeconds
                    },this),
                    this.drain()) : (this.blocked = !0,
                    this.deregisterDrain())
                }
                )),
                !0 === e.init.spa.enabled) {
                    t.initialPageLoad = new y("initialPageLoad",0,t.lastSeenUrl,t.lastSeenRouteName,te,e.agentIdentifier),
                    t.initialPageLoad.save = !0,
                    t.prevInteraction = t.initialPageLoad,
                    t.currentNode = t.initialPageLoad.root,
                    t.initialPageLoad[K]++,
                    (0,
                    r.i)(H, N, this.featureName, c),
                    (0,
                    r.i)(B, N, this.featureName, l);
                    var R = {
                        getCurrentNode: function() {
                            return t.currentNode
                        },
                        setCurrentNode: ee
                    };
                    (0,
                    r.i)("spa-register", (function(e) {
                        "function" == typeof e && e(R)
                    }
                    ), A.K7.spa, c),
                    (0,
                    r.i)(_, I, this.featureName, c),
                    (0,
                    r.i)("cb-end", I, this.featureName, l),
                    (0,
                    r.i)(H, (function(i, r) {
                        var s = i[0]
                          , n = s.type
                          , a = s["__nrNode:".concat(C.W)];
                        if (!t.pageLoaded && ("load" === n && r === window || h.A4) && (t.pageLoaded = !0,
                        this.prevNode = t.currentNode = null,
                        t.initialPageLoad && (a = t.initialPageLoad.root,
                        t.initialPageLoad[K] = 0,
                        X((function() {
                            L.push("popstate")
                        }
                        )))),
                        a)
                            ee(a);
                        else if ("hashchange" === n)
                            ee(t.nodeOnLastHashUpdate),
                            t.nodeOnLastHashUpdate = null;
                        else if (r instanceof XMLHttpRequest)
                            ee(c.context(r).spaNode);
                        else if (!t.currentNode && -1 !== L.indexOf(n)) {
                            var o = new y(n,this[H],t.lastSeenUrl,t.lastSeenRouteName,te,e.agentIdentifier);
                            if (t.prevInteraction = o,
                            ee(o.root),
                            "click" === n) {
                                var u = function(e) {
                                    var t = e.tagName.toLowerCase();
                                    if (-1 !== ["a", "button", "input"].indexOf(t))
                                        return e.title || e.value || e.innerText
                                }(s.target);
                                u && (t.currentNode.attrs.custom.actionText = u)
                            }
                        }
                        s["__nrNode:".concat(C.W)] = t.currentNode
                    }
                    ), this.featureName, f),
                    (0,
                    r.i)("setTimeout-end", (function(e, i, r) {
                        !t.currentNode || t.timerBudget - this.timerDuration < 0 || (!e || e[0]instanceof Function) && (t.currentNode[z][K]++,
                        this.timerId = r,
                        t.timerMap[r] = t.currentNode,
                        this.timerBudget = t.timerBudget - 50)
                    }
                    ), this.featureName, p),
                    (0,
                    r.i)("clearTimeout-start", (function(e) {
                        var i = e[0]
                          , r = t.timerMap[i];
                        if (r) {
                            var s = r[z];
                            s[K]--,
                            s.checkFinish(),
                            delete t.timerMap[i]
                        }
                    }
                    ), this.featureName, p),
                    (0,
                    r.i)(H, (function() {
                        t.timerBudget = this.timerBudget || D;
                        var e = this.timerId
                          , i = t.timerMap[e];
                        ee(i),
                        delete t.timerMap[e],
                        i && i[z][K]--
                    }
                    ), this.featureName, p),
                    (0,
                    r.i)(H, (function() {
                        ee(this[V])
                    }
                    ), this.featureName, b),
                    (0,
                    r.i)("new-xhr", (function() {
                        if (!t.disableSpaFix && !t.currentNode && t.prevInteraction && !t.prevInteraction.ignored) {
                            const e = t.prevInteraction;
                            t.currentNode = e.root,
                            e.root.end = null
                        }
                        t.currentNode && (this[V] = t.currentNode.child("ajax", null, null, !0))
                    }
                    ), this.featureName, b),
                    (0,
                    r.i)("send-xhr-start", (function() {
                        var t = this[V];
                        t && !this.sent && (this.sent = !0,
                        t.dt = this.dt,
                        t.dt?.timestamp && (t.dt.timestamp = e.runtime.timeKeeper.correctAbsoluteTimestamp(t.dt.timestamp)),
                        t.jsEnd = t.start = this.startTime,
                        t[z][K]++)
                    }
                    ), this.featureName, b),
                    (0,
                    r.i)("xhr-resolved", (function() {
                        var e = this[V];
                        if (e) {
                            if (!(0,
                            n.gX)(this.params))
                                return void e.cancel();
                            var t = e.attrs;
                            t.params = this.params,
                            t.metrics = this.metrics,
                            e.finish(this.endTime),
                            this.currentNode && this.currentNode.interaction && this.currentNode.interaction.checkFinish()
                        }
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)("new-jsonp", (function(e) {
                        t.currentNode && ((this[q] = t.currentNode.child("ajax", this[G])).start = this["new-jsonp"],
                        this.url = e,
                        this.status = null)
                    }
                    ), this.featureName, v),
                    (0,
                    r.i)("cb-start", (function(e) {
                        var t = this[q];
                        t && (ee(t),
                        this.status = 200)
                    }
                    ), this.featureName, v),
                    (0,
                    r.i)("jsonp-error", (function() {
                        var e = this[q];
                        e && (ee(e),
                        this.status = 0)
                    }
                    ), this.featureName, v),
                    (0,
                    r.i)(Z, (function() {
                        var e = this[q];
                        if (e) {
                            if (null === this.status)
                                return void e.cancel();
                            var t = e.attrs
                              , i = t.params = {}
                              , r = (0,
                            s.D)(this.url);
                            i.method = "GET",
                            i.pathname = r.pathname,
                            i.host = r.hostname + ":" + r.port,
                            i.status = this.status,
                            t.metrics = {
                                txSize: 0,
                                rxSize: 0
                            },
                            t.isJSONP = !0,
                            e.jsEnd = this[Z],
                            e.jsTime = this[B] ? this[Z] - this[B] : 0,
                            e.finish(e.jsEnd)
                        }
                    }
                    ), this.featureName, v),
                    (0,
                    r.i)(G, (function(i, r) {
                        if (i) {
                            if (!t.disableSpaFix && !t.currentNode && t.prevInteraction && !t.prevInteraction.ignored) {
                                const e = t.prevInteraction;
                                t.currentNode = e.root,
                                e.root.end = null
                            }
                            t.currentNode && (this[V] = t.currentNode.child("ajax", this[G]),
                            r && this[V] && (this[V].dt = r,
                            this[V].dt?.timestamp && (this[V].dt.timestamp = e.runtime.timeKeeper.correctAbsoluteTimestamp(this[V].dt.timestamp))))
                        }
                    }
                    ), this.featureName, g),
                    (0,
                    r.i)(W + "start", (function(e) {
                        t.currentNode && (this[V] = t.currentNode,
                        t.currentNode[z][K]++)
                    }
                    ), this.featureName, g),
                    (0,
                    r.i)(W + "end", (function(e, t, i) {
                        var r = this[V];
                        r && r[z][K]--
                    }
                    ), this.featureName, g),
                    (0,
                    r.i)(J, (function(e, t) {
                        var i = this[V];
                        if (i) {
                            if (e || !(0,
                            n.gX)(this.params))
                                return void i.cancel();
                            var r = i.attrs;
                            r.params = this.params,
                            r.metrics = {
                                txSize: this.txSize,
                                rxSize: this.rxSize
                            },
                            r.isFetch = !0,
                            i.finish(this[J])
                        }
                    }
                    ), this.featureName, g),
                    (0,
                    r.i)("newURL", (function(e, i) {
                        if (t.currentNode)
                            t.currentNode[z].setNewURL(e);
                        else if (t.prevInteraction && !t.prevInteraction.ignored) {
                            const i = t.prevInteraction;
                            i.setNewURL(e),
                            i.root.end = null,
                            ee(i.root)
                        }
                        t.currentNode && (t.lastSeenUrl !== e && (t.currentNode[z].routeChange = !0),
                        i && (t.nodeOnLastHashUpdate = t.currentNode)),
                        t.lastSeenUrl = e
                    }
                    ), this.featureName, m),
                    v.on("dom-start", (function(e) {
                        if (t.currentNode) {
                            var i = e[0]
                              , r = i && "SCRIPT" === i.nodeName && "" !== i.src
                              , s = t.currentNode.interaction;
                            r && (s[K]++,
                            i.addEventListener("load", (function() {
                                s[K]--,
                                s.checkFinish()
                            }
                            ), (0,
                            T.jT)(!1)),
                            i.addEventListener("error", (function() {
                                s[K]--,
                                s.checkFinish()
                            }
                            ), (0,
                            T.jT)(!1)))
                        }
                    }
                    )),
                    (0,
                    r.i)(H, (function() {
                        ee(t.prevNode)
                    }
                    ), this.featureName, u),
                    (0,
                    r.i)("resolve-start", Y, this.featureName, l),
                    (0,
                    r.i)("executor-err", Y, this.featureName, l),
                    (0,
                    r.i)("propagate", (function(e, i) {
                        !i && this[V] || (this[V] = t.currentNode)
                    }
                    ), this.featureName, l),
                    (0,
                    r.i)(B, (function() {
                        ee((this.getCtx ? this.getCtx() : this)[V])
                    }
                    ), this.featureName, l),
                    (0,
                    r.i)(U + "get", (function(i) {
                        var r;
                        r = this.ixn = t?.currentNode?.[z] ? t.currentNode[z] : null === t?.prevNode?.end && "initialPageLoad" !== t?.prevNode?.[z]?.root?.[z]?.eventName ? t.prevNode[z] : new y("api",i,t.lastSeenUrl,t.lastSeenRouteName,te,e.agentIdentifier),
                        t.currentNode || (r.checkFinish(),
                        t.depth && ee(r.root))
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "actionText", (function(e, t) {
                        var i = this.ixn.root.attrs.custom;
                        t && (i.actionText = t)
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "setName", (function(e, t, i) {
                        var r = this.ixn.root.attrs;
                        t && (r.customName = t),
                        i && (r.trigger = i)
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "setAttribute", (function(e, t, i) {
                        this.ixn.root.attrs.custom[t] = i
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "end", (function(e) {
                        var t = this.ixn
                          , i = Q(t);
                        ee(null),
                        i.child("customEnd", e)?.finish(e),
                        t.finish()
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "ignore", (function(e) {
                        this.ixn.ignored = !0
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "save", (function(e) {
                        this.ixn.save = !0
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "tracer", (function(e, t, i) {
                        var r = this.ixn
                          , s = Q(r)
                          , n = c.context(i);
                        if (!t)
                            return n.inc = ++r[K],
                            n[V] = s;
                        n[V] = s.child("customTracer", e, t)
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(H, x, this.featureName, w),
                    (0,
                    r.i)("no-" + H, x, this.featureName, w),
                    (0,
                    r.i)(U + "getContext", (function(e, t) {
                        var i = this.ixn.root.attrs.store;
                        setTimeout((function() {
                            t(i)
                        }
                        ), 0)
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)(U + "onEnd", (function(e, t) {
                        this.ixn.handlers.push(t)
                    }
                    ), this.featureName, c),
                    (0,
                    r.i)("api-routeName", (function(e, i) {
                        t.lastSeenRouteName = i,
                        t.currentNode && t.currentNode[z].setNewRoute(i)
                    }
                    ), this.featureName, c),
                    c.on("spa-jserror", (function(e, i, r, s) {
                        t.currentNode && (r._interactionId = t.currentNode.interaction.id,
                        t.currentNode.type && "interaction" !== t.currentNode.type && (r._interactionNodeId = t.currentNode.id))
                    }
                    )),
                    (0,
                    r.i)("function-err", (function(i, r, s) {
                        t.currentNode && (s.__newrelic ??= {},
                        s.__newrelic[e.agentIdentifier] = {
                            interactionId: t.currentNode.interaction.id
                        },
                        t.currentNode.type && "interaction" !== t.currentNode.type && (s.__newrelic[e.agentIdentifier].interactionNodeId = t.currentNode.id))
                    }
                    ), this.featureName, c),
                    c.on("interaction", (function(e) {
                        if (e.ignored || !e.save && !e.routeChange)
                            return void c.emit("interactionDone", [e, !1]);
                        t.prevInteraction === e && (t.prevInteraction = null);
                        e.root.attrs.id = (0,
                        o.bz)(),
                        "initialPageLoad" === e.root.attrs.trigger && (e.root.attrs.firstPaint = M.J.current.value,
                        e.root.attrs.firstContentfulPaint = k.j.current.value);
                        let r;
                        c.emit("interactionDone", [e, !0]),
                        i.events.add(e),
                        r = "initialPageLoad" === e.root?.attrs?.trigger ? "InitialPageLoad" : e.routeChange ? "RouteChange" : "Custom";
                        (0,
                        F.p)(O.xV, ["Spa/Interaction/".concat(r, "/Duration/Ms"), Math.max((e.root?.end || 0) - (e.root?.start || 0), 0)], void 0, A.K7.metrics, c),
                        a?.scheduleHarvest(0),
                        a || (0,
                        j.R)(19)
                    }
                    ))
                }
                function N() {
                    t.depth++,
                    this.prevNode = t.currentNode,
                    this.ct = t.childTime,
                    t.childTime = 0,
                    t.timerBudget = D
                }
                function I() {
                    t.depth--;
                    var e = this.jsTime || 0
                      , i = e - t.childTime;
                    t.childTime = this.ct + e,
                    t.currentNode && (t.currentNode.callback(i, this[_]),
                    this.isTraced && (t.currentNode.attrs.tracedTime = i)),
                    this.jsTime = t.currentNode ? 0 : i,
                    ee(this.prevNode),
                    this.prevNode = null,
                    t.timerBudget = D
                }
                function x(e, t, i) {
                    var r = this[V];
                    if (r) {
                        var s = r[z]
                          , n = this.inc;
                        this.isTraced = !0,
                        n ? s[K]-- : r && r.finish(e),
                        i ? ee(r) : s.checkFinish()
                    }
                }
                function Q(e) {
                    return t.currentNode && t.currentNode[z] === e ? t.currentNode : e.root
                }
                function Y() {
                    this.resolved || (this.resolved = !0,
                    this[V] = t.currentNode)
                }
                function ee(e) {
                    t.pageLoaded || e || !t.initialPageLoad || (e = t.initialPageLoad.root),
                    t.currentNode && t.currentNode[z].checkFinish(),
                    t.prevNode = t.currentNode,
                    t.currentNode = e && !e[z].root.end ? e : null
                }
                function te(e) {
                    e === t.initialPageLoad && (t.initialPageLoad = null);
                    var i = e.root
                      , r = i.attrs;
                    t.currentNode = i,
                    Object.values(e.handlers || {}).forEach((function(e) {
                        e(r.store)
                    }
                    )),
                    ee(null)
                }
            }
            serializer(e) {
                return this.spaSerializerClass.serializeMultiple(e, 0, a.ss)
            }
        }
    }
    ,
    6526: (e, t, i) => {
        i.d(t, {
            setupAgentSession: () => N
        });
        var r = i(1687)
          , s = i(7836)
          , n = i(3606)
          , a = i(9566)
          , o = i(944)
          , c = i(3304);
        class h {
            constructor(e, t) {
                if (!e.onEnd)
                    throw new Error("onEnd handler is required");
                if (!t)
                    throw new Error("ms duration is required");
                this.onEnd = e.onEnd,
                this.initialMs = t,
                this.startTimestamp = Date.now(),
                this.timer = this.create(this.onEnd, t)
            }
            create(e, t) {
                return this.timer && this.clear(),
                setTimeout(( () => e ? e() : this.onEnd()), t || this.initialMs)
            }
            clear() {
                clearTimeout(this.timer),
                this.timer = null
            }
            end() {
                this.clear(),
                this.onEnd()
            }
            isValid() {
                return this.initialMs - (Date.now() - this.startTimestamp) > 0
            }
        }
        var u = i(6154)
          , d = i(2614)
          , l = i(2843)
          , m = i(6389);
        class f extends h {
            constructor(e, t) {
                super(e, t),
                this.onPause = "function" == typeof e.onPause ? e.onPause : () => {}
                ,
                this.onRefresh = "function" == typeof e.onRefresh ? e.onRefresh : () => {}
                ,
                this.onResume = "function" == typeof e.onResume ? e.onResume : () => {}
                ,
                this.readStorage = e.readStorage,
                this.remainingMs = void 0,
                e.refreshEvents || (e.refreshEvents = ["click", "keydown", "scroll"]);
                try {
                    this.abortController = new AbortController
                } catch (e) {}
                if (u.RI && e.ee) {
                    if (e.ee) {
                        this.ee = e.ee;
                        const t = (0,
                        m.s)(this.refresh.bind(this), 500, {
                            leading: !0
                        });
                        this.refreshHandler = i => {
                            e.refreshEvents.includes(i?.[0]?.type) && t()
                        }
                        ,
                        e.ee.on("fn-end", this.refreshHandler)
                    }
                    (0,
                    l.u)((e => {
                        "hidden" === e ? this.pause() : this.resume()
                    }
                    ), !1, !1, this.abortController?.signal)
                }
            }
            abort() {
                this.clear(),
                this.abortController?.abort(),
                this.refreshHandler && (this.ee.removeEventListener("fn-end", this.refreshHandler),
                this.refreshHandler = this.ee = null)
            }
            pause() {
                this.onPause(),
                clearTimeout(this.timer),
                this.remainingMs = this.initialMs - (Date.now() - this.startTimestamp)
            }
            resume() {
                try {
                    const t = this.readStorage()
                      , i = "string" == typeof t ? JSON.parse(t) : t;
                    e(i.expiresAt) || e(i.inactiveAt) ? this.end() : (this.refresh(),
                    this.onResume())
                } catch (e) {
                    this.end()
                }
                function e(e) {
                    return Date.now() > e
                }
            }
            refresh(e, t) {
                this.clear(),
                this.timer = this.create(e, t),
                this.startTimestamp = Date.now(),
                this.remainingMs = void 0,
                this.onRefresh()
            }
        }
        var p = i(8139)
          , g = i(8122)
          , v = i(9908)
          , y = i(3969)
          , b = i(860)
          , T = i(3878);
        const S = {
            value: "",
            inactiveAt: 0,
            expiresAt: 0,
            updatedAt: Date.now(),
            sessionReplayMode: d.g.OFF,
            sessionReplaySentFirstChunk: !1,
            sessionTraceMode: d.g.OFF,
            traceHarvestStarted: !1,
            serverTimeDiff: null,
            custom: {}
        };
        class w {
            constructor(e) {
                const {agentIdentifier: t, key: i, storage: r} = e;
                if (!t || !i || !r)
                    throw new Error("Missing required field(s):".concat(t ? "" : " agentID").concat(i ? "" : " key").concat(r ? "" : " storage"));
                this.agentIdentifier = t,
                this.storage = r,
                this.state = {},
                this.key = i,
                this.ee = s.ee.get(t),
                (0,
                p.u)(this.ee),
                this.setup(e),
                u.RI && (0,
                T.sp)("storage", (e => {
                    if (e.key === this.lookupKey) {
                        const t = "string" == typeof e.newValue ? JSON.parse(e.newValue) : e.newValue;
                        this.sync(t),
                        this.ee.emit(d.tS.UPDATE, [d.iL.CROSS_TAB, this.state])
                    }
                }
                ))
            }
            setup({value: e=(0,
            a.LA)(16), expiresMs: t=d.wk, inactiveMs: i=d.BB}) {
                const r = {
                    serverTimeDiff: this.state.serverTimeDiff || S.serverTimeDiff
                };
                this.state = {},
                this.sync({
                    ...S,
                    ...r
                }),
                this.state.value = e,
                this.expiresMs = t,
                this.inactiveMs = i;
                const s = this.read();
                t ? (this.state.expiresAt = s?.expiresAt || this.getFutureTimestamp(t),
                this.expiresTimer = new h({
                    onEnd: () => {
                        this.collectSM("expired"),
                        this.collectSM("duration"),
                        this.reset()
                    }
                },this.state.expiresAt - Date.now())) : this.state.expiresAt = 1 / 0,
                i ? (this.state.inactiveAt = s?.inactiveAt || this.getFutureTimestamp(i),
                this.inactiveTimer = new f({
                    onEnd: () => {
                        this.collectSM("inactive"),
                        this.collectSM("duration"),
                        this.reset()
                    }
                    ,
                    onRefresh: this.refresh.bind(this),
                    onResume: () => {
                        this.ee.emit(d.tS.RESUME)
                    }
                    ,
                    onPause: () => {
                        this.initialized && this.ee.emit(d.tS.PAUSE),
                        this.write((0,
                        g.a)(this.state, S))
                    }
                    ,
                    ee: this.ee,
                    refreshEvents: ["click", "keydown", "scroll"],
                    readStorage: () => this.storage.get(this.lookupKey)
                },this.state.inactiveAt - Date.now())) : this.state.inactiveAt = 1 / 0,
                this.isNew ||= !Object.keys(s).length,
                this.isNew ? this.write((0,
                g.a)(this.state, S), !0) : this.sync(s),
                this.initialized = !0,
                this.ee.emit(d.tS.STARTED, [this.isNew])
            }
            get lookupKey() {
                return "".concat(d.H3, "_").concat(this.key)
            }
            sync(e) {
                Object.assign(this.state, e)
            }
            read() {
                try {
                    const e = this.storage.get(this.lookupKey);
                    if (!e)
                        return {};
                    const t = "string" == typeof e ? JSON.parse(e) : e;
                    return this.isInvalid(t) ? {} : this.isExpired(t.expiresAt) ? (this.collectSM("expired"),
                    this.collectSM("duration", t, !0),
                    this.reset()) : this.isExpired(t.inactiveAt) ? (this.collectSM("inactive"),
                    this.collectSM("duration", t, !0),
                    this.reset()) : t
                } catch (e) {
                    return (0,
                    o.R)(10, e),
                    {}
                }
            }
            write(e) {
                try {
                    if (!e || "object" != typeof e)
                        return;
                    return e.updatedAt = Date.now(),
                    this.sync(e),
                    this.storage.set(this.lookupKey, (0,
                    c.A)(this.state)),
                    this.ee.emit(d.tS.UPDATE, [d.iL.SAME_TAB, this.state]),
                    e
                } catch (e) {
                    return (0,
                    o.R)(11, e),
                    null
                }
            }
            reset() {
                try {
                    return this.initialized && this.ee.emit(d.tS.RESET),
                    this.storage.remove(this.lookupKey),
                    this.inactiveTimer?.abort?.(),
                    this.expiresTimer?.clear?.(),
                    delete this.isNew,
                    this.setup({
                        agentIdentifier: this.agentIdentifier,
                        key: this.key,
                        storage: this.storage,
                        expiresMs: this.expiresMs,
                        inactiveMs: this.inactiveMs
                    }),
                    this.read()
                } catch (e) {
                    return {}
                }
            }
            refresh() {
                const e = this.read();
                this.write({
                    ...e,
                    inactiveAt: this.getFutureTimestamp(this.inactiveMs)
                })
            }
            isExpired(e) {
                return Date.now() > e
            }
            isInvalid(e) {
                return !Object.keys(S).every((t => Object.keys(e).includes(t)))
            }
            collectSM(e, t, i) {
                let r, s;
                "duration" === e && (r = this.getDuration(t, i),
                s = "Session/Duration/Ms"),
                "expired" === e && (s = "Session/Expired/Seen"),
                "inactive" === e && (s = "Session/Inactive/Seen"),
                s && (0,
                v.p)(y.xV, [s, r], void 0, b.K7.metrics, this.ee)
            }
            getDuration(e=this.state, t) {
                const i = e.expiresAt - this.expiresMs;
                return (t ? Date.now() : e.updatedAt) - i
            }
            getFutureTimestamp(e) {
                return Date.now() + e
            }
            syncCustomAttribute(e, t) {
                if (u.RI)
                    if (null === t) {
                        const t = this.read();
                        t.custom && (delete t.custom[e],
                        this.write({
                            ...t
                        }))
                    } else {
                        const i = this.read();
                        this.custom = {
                            ...i?.custom || {},
                            [e]: t
                        },
                        this.write({
                            ...i,
                            custom: this.custom
                        })
                    }
            }
        }
        class R {
            get(e) {
                try {
                    return localStorage.getItem(e) || void 0
                } catch (e) {
                    return ""
                }
            }
            set(e, t) {
                try {
                    return null == t ? this.remove(e) : localStorage.setItem(e, t)
                } catch (e) {}
            }
            remove(e) {
                try {
                    localStorage.removeItem(e)
                } catch (e) {}
            }
        }
        function N(e) {
            if (e.runtime.session)
                return e.runtime.session;
            const t = e.init.session;
            e.runtime.session = new w({
                agentIdentifier: e.agentIdentifier,
                key: d.uh,
                storage: new R,
                expiresMs: t?.expiresMs,
                inactiveMs: t?.inactiveMs
            });
            const i = e.runtime.session.state.custom;
            i && (e.info.jsAttributes = {
                ...e.info.jsAttributes,
                ...i
            });
            const a = s.ee.get(e.agentIdentifier);
            return (0,
            n.i)("api-setCustomAttribute", ( (t, i, r) => {
                e.runtime.session.syncCustomAttribute(i, r)
            }
            ), "session", a),
            (0,
            n.i)("api-setUserId", ( (t, i, r) => {
                e.runtime.session.syncCustomAttribute(i, r)
            }
            ), "session", a),
            (0,
            r.Ze)(e.agentIdentifier, "session"),
            e.runtime.session
        }
    }
    ,
    5942: (e, t, i) => {
        i.d(t, {
            r: () => p
        });
        var r = i(4234)
          , s = i(2555)
          , n = i(425)
          , a = i(384)
          , o = i(1687)
          , c = i(5284)
          , h = i(9417)
          , u = i(4284)
          , d = i(944);
        class l {
            #w;
            constructor(e) {
                this.#w = l.getRuleValidationCache(e),
                l.logObfuscationRuleErrors(this.#w)
            }
            get ruleValidationCache() {
                return this.#w
            }
            obfuscateString(e) {
                return "string" != typeof e || 0 === e.trim().length ? e : this.#w.filter((e => e.isValid)).reduce(( (e, t) => {
                    const {rule: i} = t;
                    return e.replace(i.regex, i.replacement || "*")
                }
                ), e)
            }
            static getRuleValidationCache(e) {
                let t = (0,
                h.gD)(e, "obfuscate") || [];
                return (0,
                u.p)() && t.push({
                    regex: /^file:\/\/(.*)/,
                    replacement: atob("ZmlsZTovL09CRlVTQ0FURUQ=")
                }),
                t.map((e => l.validateObfuscationRule(e)))
            }
            static validateObfuscationRule(e) {
                const t = Boolean(void 0 === e.regex)
                  , i = Boolean(void 0 !== e.regex && "string" != typeof e.regex && !(e.regex instanceof RegExp))
                  , r = Boolean(e.replacement && "string" != typeof e.replacement);
                return {
                    rule: e,
                    isValid: !t && !i && !r,
                    errors: {
                        regexMissingDetected: t,
                        invalidRegexDetected: i,
                        invalidReplacementDetected: r
                    }
                }
            }
            static logObfuscationRuleErrors(e) {
                for (const t of e) {
                    const {rule: e, isValid: i, errors: r} = t;
                    i || (r.regexMissingDetected ? (0,
                    d.R)(12, e) : r.invalidRegexDetected && (0,
                    d.R)(13, e),
                    r.invalidReplacementDetected && (0,
                    d.R)(14, e))
                }
            }
        }
        var m = i(8771)
          , f = i(860);
        class p extends r.W {
            constructor(e, t) {
                super(e.agentIdentifier, t),
                this.agentRef = e,
                [f.K7.jserrors, f.K7.metrics].includes(this.featureName) ? this.events = e.sharedAggregator : [f.K7.pageViewEvent, f.K7.sessionTrace].includes(this.featureName) || (this.events = new m.Z),
                this.checkConfiguration(e),
                this.obfuscator = e.runtime.obfuscator
            }
            waitForFlags(e=[]) {
                return new Promise(( (t, i) => {
                    function r(t) {
                        return e.map((e => t[e] ? t[e] : 0))
                    }
                    c.B[this.agentIdentifier] ? t(r(c.B[this.agentIdentifier])) : this.ee.on("rumresp", ( (e={}) => {
                        t(r(e))
                    }
                    ))
                }
                )).catch((e => {
                    this.ee.emit("internal-error", [e]),
                    this.blocked = !0,
                    this.deregisterDrain()
                }
                ))
            }
            drain() {
                (0,
                o.Ze)(this.agentIdentifier, this.featureName),
                this.drained = !0
            }
            makeHarvestPayload(e=!1, t={}) {
                if (this.events.isEmpty(t))
                    return;
                if (this.preHarvestChecks && !this.preHarvestChecks())
                    return;
                e && this.events.save(t);
                const i = this.events.get(t)
                  , r = this.serializer ? this.serializer(i) : i;
                this.events.clear(t);
                const s = {
                    body: r
                };
                return this.queryStringsBuilder && (s.qs = this.queryStringsBuilder(i)),
                s
            }
            postHarvestCleanup(e=!1, t={}) {
                e && this.events.reloadSave(t),
                this.events.clearSave(t)
            }
            checkConfiguration(e) {
                if (!(0,
                s.fn)(this.agentIdentifier)) {
                    const t = (0,
                    a.pV)();
                    let i = {
                        ...t.info?.jsAttributes
                    };
                    try {
                        i = {
                            ...i,
                            ...e.info?.jsAttributes
                        }
                    } catch (e) {}
                    (0,
                    n.j)({
                        agentIdentifier: this.agentIdentifier
                    }, {
                        ...t,
                        info: {
                            ...t.info,
                            jsAttributes: i
                        },
                        runtime: e.runtime
                    })
                }
                e.runtime.obfuscator || (e.runtime.obfuscator = new l(this.agentIdentifier))
            }
        }
    }
    ,
    8771: (e, t, i) => {
        i.d(t, {
            Z: () => n
        });
        var r = i(3304)
          , s = i(7699);
        class n {
            #R = [];
            #N = 0;
            #E;
            #I;
            constructor(e=s.I) {
                this.maxPayloadSize = e
            }
            isEmpty() {
                return 0 === this.#R.length
            }
            get() {
                return this.#R
            }
            byteSize() {
                return this.#N
            }
            wouldExceedMaxSize(e) {
                return this.#N + e > this.maxPayloadSize
            }
            add(e) {
                const t = (0,
                r.A)(e)?.length || 0;
                return !(this.#N + t > this.maxPayloadSize) && (this.#R.push(e),
                this.#N += t,
                !0)
            }
            clear() {
                this.#R = [],
                this.#N = 0
            }
            save() {
                this.#E = this.#R,
                this.#I = this.#N
            }
            clearSave() {
                this.#E = void 0,
                this.#I = void 0
            }
            reloadSave() {
                this.#E && (this.#I + this.#N > this.maxPayloadSize || (this.#R = [...this.#E, ...this.#R],
                this.#N = this.#I + this.#N))
            }
        }
    }
    ,
    6103: (e, t, i) => {
        i.d(t, {
            lazyFeatureLoader: () => s
        });
        var r = i(860);
        function s(e, t) {
            if ("aggregate" === t)
                switch (e) {
                case r.K7.ajax:
                    return i.e(478).then(i.bind(i, 1038));
                case r.K7.jserrors:
                    return i.e(478).then(i.bind(i, 5928));
                case r.K7.genericEvents:
                    return i.e(478).then(i.bind(i, 8019));
                case r.K7.logging:
                    return i.e(478).then(i.bind(i, 5288));
                case r.K7.metrics:
                    return i.e(478).then(i.bind(i, 8351));
                case r.K7.pageViewEvent:
                    return i.e(478).then(i.bind(i, 1983));
                case r.K7.pageViewTiming:
                    return i.e(478).then(i.bind(i, 5999));
                case r.K7.sessionReplay:
                    return i.e(478).then(i.bind(i, 6167));
                case r.K7.sessionTrace:
                    return i.e(478).then(i.bind(i, 575));
                case r.K7.spa:
                    return i.e(478).then(i.bind(i, 5592));
                case r.K7.softNav:
                    return i.e(478).then(i.bind(i, 4393));
                default:
                    throw new Error("Attempted to load unsupported agent feature: ".concat(e, " ").concat(t))
                }
        }
    }
    ,
    8778: (e, t, i) => {
        i.r(t),
        i.d(t, {
            setAPI: () => d
        });
        var r = i(860)
          , s = i(3371)
          , n = i(7836)
          , a = i(9908)
          , o = i(3606)
          , c = i(6389)
          , h = i(3969)
          , u = i(6154);
        function d(e) {
            var t = n.ee.get(e)
              , i = {
                finished: (0,
                c.J)((function(e, i) {
                    var s = i ? i - u.WN : e;
                    (0,
                    a.p)(h.XG, ["finished", {
                        time: s
                    }], void 0, r.K7.metrics, t),
                    d(e, {
                        name: "finished",
                        start: s + u.WN,
                        origin: "nr"
                    }),
                    (0,
                    a.p)("api-addPageAction", [s, "finished"], void 0, r.K7.genericEvents, t)
                }
                )),
                setErrorHandler: function(t, i) {
                    (0,
                    s.f)(e).onerror = i
                },
                addToTrace: d,
                addRelease: function(t, i, r) {
                    if (++l > 10)
                        return;
                    (0,
                    s.f)(e).releaseIds[i.slice(-200)] = ("" + r).slice(-200)
                }
            };
            function d(e, i) {
                if (i && "object" == typeof i && i.name && i.start) {
                    var s = {
                        n: i.name,
                        s: i.start - u.WN,
                        e: (i.end || i.start) - u.WN,
                        o: i.origin || "",
                        t: "api"
                    };
                    (0,
                    a.p)("bstApi", [s], void 0, r.K7.sessionTrace, t)
                }
            }
            Object.entries(i).forEach(( ([e,i]) => (0,
            o.i)("api-" + e, i, "api", t)));
            var l = 0
        }
    }
    ,
    7226: (e, t, i) => {
        i.d(t, {
            Ck: () => le,
            IN: () => k,
            fK: () => ce,
            lt: () => Te,
            rH: () => ne,
            zB: () => M
        });
        var r, s, n = function() {
            var e = self.performance && performance.getEntriesByType && performance.getEntriesByType("navigation")[0];
            if (e && e.responseStart > 0 && e.responseStart < performance.now())
                return e
        }, a = function(e) {
            if ("loading" === document.readyState)
                return "loading";
            var t = n();
            if (t) {
                if (e < t.domInteractive)
                    return "loading";
                if (0 === t.domContentLoadedEventStart || e < t.domContentLoadedEventStart)
                    return "dom-interactive";
                if (0 === t.domComplete || e < t.domComplete)
                    return "dom-content-loaded"
            }
            return "complete"
        }, o = function(e) {
            var t = e.nodeName;
            return 1 === e.nodeType ? t.toLowerCase() : t.toUpperCase().replace(/^#/, "")
        }, c = function(e, t) {
            var i = "";
            try {
                for (; e && 9 !== e.nodeType; ) {
                    var r = e
                      , s = r.id ? "#" + r.id : o(r) + (r.classList && r.classList.value && r.classList.value.trim() && r.classList.value.trim().length ? "." + r.classList.value.trim().replace(/\s+/g, ".") : "");
                    if (i.length + s.length > (t || 100) - 1)
                        return i || s;
                    if (i = i ? s + ">" + i : s,
                    r.id)
                        break;
                    e = r.parentNode
                }
            } catch (e) {}
            return i
        }, h = -1, u = function() {
            return h
        }, d = function(e) {
            addEventListener("pageshow", (function(t) {
                t.persisted && (h = t.timeStamp,
                e(t))
            }
            ), !0)
        }, l = function() {
            var e = n();
            return e && e.activationStart || 0
        }, m = function(e, t) {
            var i = n()
              , r = "navigate";
            return u() >= 0 ? r = "back-forward-cache" : i && (document.prerendering || l() > 0 ? r = "prerender" : document.wasDiscarded ? r = "restore" : i.type && (r = i.type.replace(/_/g, "-"))),
            {
                name: e,
                value: void 0 === t ? -1 : t,
                rating: "good",
                delta: 0,
                entries: [],
                id: "v4-".concat(Date.now(), "-").concat(Math.floor(8999999999999 * Math.random()) + 1e12),
                navigationType: r
            }
        }, f = function(e, t, i) {
            try {
                if (PerformanceObserver.supportedEntryTypes.includes(e)) {
                    var r = new PerformanceObserver((function(e) {
                        Promise.resolve().then((function() {
                            t(e.getEntries())
                        }
                        ))
                    }
                    ));
                    return r.observe(Object.assign({
                        type: e,
                        buffered: !0
                    }, i || {})),
                    r
                }
            } catch (e) {}
        }, p = function(e, t, i, r) {
            var s, n;
            return function(a) {
                t.value >= 0 && (a || r) && ((n = t.value - (s || 0)) || void 0 === s) && (s = t.value,
                t.delta = n,
                t.rating = function(e, t) {
                    return e > t[1] ? "poor" : e > t[0] ? "needs-improvement" : "good"
                }(t.value, i),
                e(t))
            }
        }, g = function(e) {
            requestAnimationFrame((function() {
                return requestAnimationFrame((function() {
                    return e()
                }
                ))
            }
            ))
        }, v = function(e) {
            document.addEventListener("visibilitychange", (function() {
                "hidden" === document.visibilityState && e()
            }
            ))
        }, y = function(e) {
            var t = !1;
            return function() {
                t || (e(),
                t = !0)
            }
        }, b = -1, T = function() {
            return "hidden" !== document.visibilityState || document.prerendering ? 1 / 0 : 0
        }, S = function(e) {
            "hidden" === document.visibilityState && b > -1 && (b = "visibilitychange" === e.type ? e.timeStamp : 0,
            R())
        }, w = function() {
            addEventListener("visibilitychange", S, !0),
            addEventListener("prerenderingchange", S, !0)
        }, R = function() {
            removeEventListener("visibilitychange", S, !0),
            removeEventListener("prerenderingchange", S, !0)
        }, N = function() {
            return b < 0 && (b = T(),
            w(),
            d((function() {
                setTimeout((function() {
                    b = T(),
                    w()
                }
                ), 0)
            }
            ))),
            {
                get firstHiddenTime() {
                    return b
                }
            }
        }, E = function(e) {
            document.prerendering ? addEventListener("prerenderingchange", (function() {
                return e()
            }
            ), !0) : e()
        }, I = [1800, 3e3], A = function(e, t) {
            t = t || {},
            E((function() {
                var i, r = N(), s = m("FCP"), n = f("paint", (function(e) {
                    e.forEach((function(e) {
                        "first-contentful-paint" === e.name && (n.disconnect(),
                        e.startTime < r.firstHiddenTime && (s.value = Math.max(e.startTime - l(), 0),
                        s.entries.push(e),
                        i(!0)))
                    }
                    ))
                }
                ));
                n && (i = p(e, s, I, t.reportAllChanges),
                d((function(r) {
                    s = m("FCP"),
                    i = p(e, s, I, t.reportAllChanges),
                    g((function() {
                        s.value = performance.now() - r.timeStamp,
                        i(!0)
                    }
                    ))
                }
                )))
            }
            ))
        }, x = [.1, .25], k = function(e, t) {
            !function(e, t) {
                t = t || {},
                A(y((function() {
                    var i, r = m("CLS", 0), s = 0, n = [], a = function(e) {
                        e.forEach((function(e) {
                            if (!e.hadRecentInput) {
                                var t = n[0]
                                  , i = n[n.length - 1];
                                s && e.startTime - i.startTime < 1e3 && e.startTime - t.startTime < 5e3 ? (s += e.value,
                                n.push(e)) : (s = e.value,
                                n = [e])
                            }
                        }
                        )),
                        s > r.value && (r.value = s,
                        r.entries = n,
                        i())
                    }, o = f("layout-shift", a);
                    o && (i = p(e, r, x, t.reportAllChanges),
                    v((function() {
                        a(o.takeRecords()),
                        i(!0)
                    }
                    )),
                    d((function() {
                        s = 0,
                        r = m("CLS", 0),
                        i = p(e, r, x, t.reportAllChanges),
                        g((function() {
                            return i()
                        }
                        ))
                    }
                    )),
                    setTimeout(i, 0))
                }
                )))
            }((function(t) {
                var i = function(e) {
                    var t, i = {};
                    if (e.entries.length) {
                        var r = e.entries.reduce((function(e, t) {
                            return e && e.value > t.value ? e : t
                        }
                        ));
                        if (r && r.sources && r.sources.length) {
                            var s = (t = r.sources).find((function(e) {
                                return e.node && 1 === e.node.nodeType
                            }
                            )) || t[0];
                            s && (i = {
                                largestShiftTarget: c(s.node),
                                largestShiftTime: r.startTime,
                                largestShiftValue: r.value,
                                largestShiftSource: s,
                                largestShiftEntry: r,
                                loadState: a(r.startTime)
                            })
                        }
                    }
                    return Object.assign(e, {
                        attribution: i
                    })
                }(t);
                e(i)
            }
            ), t)
        }, M = function(e, t) {
            A((function(t) {
                var i = function(e) {
                    var t = {
                        timeToFirstByte: 0,
                        firstByteToFCP: e.value,
                        loadState: a(u())
                    };
                    if (e.entries.length) {
                        var i = n()
                          , r = e.entries[e.entries.length - 1];
                        if (i) {
                            var s = i.activationStart || 0
                              , o = Math.max(0, i.responseStart - s);
                            t = {
                                timeToFirstByte: o,
                                firstByteToFCP: e.value - o,
                                loadState: a(e.entries[0].startTime),
                                navigationEntry: i,
                                fcpEntry: r
                            }
                        }
                    }
                    return Object.assign(e, {
                        attribution: t
                    })
                }(t);
                e(i)
            }
            ), t)
        }, C = 0, F = 1 / 0, O = 0, j = function(e) {
            e.forEach((function(e) {
                e.interactionId && (F = Math.min(F, e.interactionId),
                O = Math.max(O, e.interactionId),
                C = O ? (O - F) / 7 + 1 : 0)
            }
            ))
        }, P = function() {
            return r ? C : performance.interactionCount || 0
        }, L = function() {
            "interactionCount"in performance || r || (r = f("event", j, {
                type: "event",
                buffered: !0,
                durationThreshold: 0
            }))
        }, D = [], H = new Map, _ = 0, B = [], U = function(e) {
            if (B.forEach((function(t) {
                return t(e)
            }
            )),
            e.interactionId || "first-input" === e.entryType) {
                var t = D[D.length - 1]
                  , i = H.get(e.interactionId);
                if (i || D.length < 10 || e.duration > t.latency) {
                    if (i)
                        e.duration > i.latency ? (i.entries = [e],
                        i.latency = e.duration) : e.duration === i.latency && e.startTime === i.entries[0].startTime && i.entries.push(e);
                    else {
                        var r = {
                            id: e.interactionId,
                            latency: e.duration,
                            entries: [e]
                        };
                        H.set(r.id, r),
                        D.push(r)
                    }
                    D.sort((function(e, t) {
                        return t.latency - e.latency
                    }
                    )),
                    D.length > 10 && D.splice(10).forEach((function(e) {
                        return H.delete(e.id)
                    }
                    ))
                }
            }
        }, K = function(e) {
            var t = self.requestIdleCallback || self.setTimeout
              , i = -1;
            return e = y(e),
            "hidden" === document.visibilityState ? e() : (i = t(e),
            v(e)),
            i
        }, z = [200, 500], V = function(e, t) {
            "PerformanceEventTiming"in self && "interactionId"in PerformanceEventTiming.prototype && (t = t || {},
            E((function() {
                var i;
                L();
                var r, s = m("INP"), n = function(e) {
                    K((function() {
                        e.forEach(U);
                        var t = function() {
                            var e = Math.min(D.length - 1, Math.floor((P() - _) / 50));
                            return D[e]
                        }();
                        t && t.latency !== s.value && (s.value = t.latency,
                        s.entries = t.entries,
                        r())
                    }
                    ))
                }, a = f("event", n, {
                    durationThreshold: null !== (i = t.durationThreshold) && void 0 !== i ? i : 40
                });
                r = p(e, s, z, t.reportAllChanges),
                a && (a.observe({
                    type: "first-input",
                    buffered: !0
                }),
                v((function() {
                    n(a.takeRecords()),
                    r(!0)
                }
                )),
                d((function() {
                    _ = P(),
                    D.length = 0,
                    H.clear(),
                    s = m("INP"),
                    r = p(e, s, z, t.reportAllChanges)
                }
                )))
            }
            )))
        }, q = [], G = [], J = 0, W = new WeakMap, Z = new Map, X = -1, Q = function(e) {
            q = q.concat(e),
            Y()
        }, Y = function() {
            X < 0 && (X = K(ee))
        }, ee = function() {
            Z.size > 10 && Z.forEach((function(e, t) {
                H.has(t) || Z.delete(t)
            }
            ));
            var e = D.map((function(e) {
                return W.get(e.entries[0])
            }
            ))
              , t = G.length - 50;
            G = G.filter((function(i, r) {
                return r >= t || e.includes(i)
            }
            ));
            for (var i = new Set, r = 0; r < G.length; r++) {
                var s = G[r];
                se(s.startTime, s.processingEnd).forEach((function(e) {
                    i.add(e)
                }
                ))
            }
            var n = q.length - 1 - 50;
            q = q.filter((function(e, t) {
                return e.startTime > J && t > n || i.has(e)
            }
            )),
            X = -1
        };
        B.push((function(e) {
            e.interactionId && e.target && !Z.has(e.interactionId) && Z.set(e.interactionId, e.target)
        }
        ), (function(e) {
            var t, i = e.startTime + e.duration;
            J = Math.max(J, e.processingEnd);
            for (var r = G.length - 1; r >= 0; r--) {
                var s = G[r];
                if (Math.abs(i - s.renderTime) <= 8) {
                    (t = s).startTime = Math.min(e.startTime, t.startTime),
                    t.processingStart = Math.min(e.processingStart, t.processingStart),
                    t.processingEnd = Math.max(e.processingEnd, t.processingEnd),
                    t.entries.push(e);
                    break
                }
            }
            t || (t = {
                startTime: e.startTime,
                processingStart: e.processingStart,
                processingEnd: e.processingEnd,
                renderTime: i,
                entries: [e]
            },
            G.push(t)),
            (e.interactionId || "first-input" === e.entryType) && W.set(e, t),
            Y()
        }
        ));
        var te, $, ie, re, se = function(e, t) {
            for (var i, r = [], s = 0; i = q[s]; s++)
                if (!(i.startTime + i.duration < e)) {
                    if (i.startTime > t)
                        break;
                    r.push(i)
                }
            return r
        }, ne = function(e, t) {
            s || (s = f("long-animation-frame", Q)),
            V((function(t) {
                var i = function(e) {
                    var t = e.entries[0]
                      , i = W.get(t)
                      , r = t.processingStart
                      , s = i.processingEnd
                      , n = i.entries.sort((function(e, t) {
                        return e.processingStart - t.processingStart
                    }
                    ))
                      , o = se(t.startTime, s)
                      , h = e.entries.find((function(e) {
                        return e.target
                    }
                    ))
                      , u = h && h.target || Z.get(t.interactionId)
                      , d = [t.startTime + t.duration, s].concat(o.map((function(e) {
                        return e.startTime + e.duration
                    }
                    )))
                      , l = Math.max.apply(Math, d)
                      , m = {
                        interactionTarget: c(u),
                        interactionTargetElement: u,
                        interactionType: t.name.startsWith("key") ? "keyboard" : "pointer",
                        interactionTime: t.startTime,
                        nextPaintTime: l,
                        processedEventEntries: n,
                        longAnimationFrameEntries: o,
                        inputDelay: r - t.startTime,
                        processingDuration: s - r,
                        presentationDelay: Math.max(l - s, 0),
                        loadState: a(t.startTime)
                    };
                    return Object.assign(e, {
                        attribution: m
                    })
                }(t);
                e(i)
            }
            ), t)
        }, ae = [2500, 4e3], oe = {}, ce = function(e, t) {
            !function(e, t) {
                t = t || {},
                E((function() {
                    var i, r = N(), s = m("LCP"), n = function(e) {
                        t.reportAllChanges || (e = e.slice(-1)),
                        e.forEach((function(e) {
                            e.startTime < r.firstHiddenTime && (s.value = Math.max(e.startTime - l(), 0),
                            s.entries = [e],
                            i())
                        }
                        ))
                    }, a = f("largest-contentful-paint", n);
                    if (a) {
                        i = p(e, s, ae, t.reportAllChanges);
                        var o = y((function() {
                            oe[s.id] || (n(a.takeRecords()),
                            a.disconnect(),
                            oe[s.id] = !0,
                            i(!0))
                        }
                        ));
                        ["keydown", "click"].forEach((function(e) {
                            addEventListener(e, (function() {
                                return K(o)
                            }
                            ), !0)
                        }
                        )),
                        v(o),
                        d((function(r) {
                            s = m("LCP"),
                            i = p(e, s, ae, t.reportAllChanges),
                            g((function() {
                                s.value = performance.now() - r.timeStamp,
                                oe[s.id] = !0,
                                i(!0)
                            }
                            ))
                        }
                        ))
                    }
                }
                ))
            }((function(t) {
                var i = function(e) {
                    var t = {
                        timeToFirstByte: 0,
                        resourceLoadDelay: 0,
                        resourceLoadDuration: 0,
                        elementRenderDelay: e.value
                    };
                    if (e.entries.length) {
                        var i = n();
                        if (i) {
                            var r = i.activationStart || 0
                              , s = e.entries[e.entries.length - 1]
                              , a = s.url && performance.getEntriesByType("resource").filter((function(e) {
                                return e.name === s.url
                            }
                            ))[0]
                              , o = Math.max(0, i.responseStart - r)
                              , h = Math.max(o, a ? (a.requestStart || a.startTime) - r : 0)
                              , u = Math.max(h, a ? a.responseEnd - r : 0)
                              , d = Math.max(u, s.startTime - r);
                            t = {
                                element: c(s.element),
                                timeToFirstByte: o,
                                resourceLoadDelay: h - o,
                                resourceLoadDuration: u - h,
                                elementRenderDelay: d - u,
                                navigationEntry: i,
                                lcpEntry: s
                            },
                            s.url && (t.url = s.url),
                            a && (t.lcpResourceEntry = a)
                        }
                    }
                    return Object.assign(e, {
                        attribution: t
                    })
                }(t);
                e(i)
            }
            ), t)
        }, he = [800, 1800], ue = function e(t) {
            document.prerendering ? E((function() {
                return e(t)
            }
            )) : "complete" !== document.readyState ? addEventListener("load", (function() {
                return e(t)
            }
            ), !0) : setTimeout(t, 0)
        }, de = function(e, t) {
            t = t || {};
            var i = m("TTFB")
              , r = p(e, i, he, t.reportAllChanges);
            ue((function() {
                var s = n();
                s && (i.value = Math.max(s.responseStart - l(), 0),
                i.entries = [s],
                r(!0),
                d((function() {
                    i = m("TTFB", 0),
                    (r = p(e, i, he, t.reportAllChanges))(!0)
                }
                )))
            }
            ))
        }, le = function(e, t) {
            de((function(t) {
                var i = function(e) {
                    var t = {
                        waitingDuration: 0,
                        cacheDuration: 0,
                        dnsDuration: 0,
                        connectionDuration: 0,
                        requestDuration: 0
                    };
                    if (e.entries.length) {
                        var i = e.entries[0]
                          , r = i.activationStart || 0
                          , s = Math.max((i.workerStart || i.fetchStart) - r, 0)
                          , n = Math.max(i.domainLookupStart - r, 0)
                          , a = Math.max(i.connectStart - r, 0)
                          , o = Math.max(i.connectEnd - r, 0);
                        t = {
                            waitingDuration: s,
                            cacheDuration: n - s,
                            dnsDuration: a - n,
                            connectionDuration: o - a,
                            requestDuration: e.value - o,
                            navigationEntry: i
                        }
                    }
                    return Object.assign(e, {
                        attribution: t
                    })
                }(t);
                e(i)
            }
            ), t)
        }, me = {
            passive: !0,
            capture: !0
        }, fe = new Date, pe = function(e, t) {
            te || (te = t,
            $ = e,
            ie = new Date,
            ye(removeEventListener),
            ge())
        }, ge = function() {
            if ($ >= 0 && $ < ie - fe) {
                var e = {
                    entryType: "first-input",
                    name: te.type,
                    target: te.target,
                    cancelable: te.cancelable,
                    startTime: te.timeStamp,
                    processingStart: te.timeStamp + $
                };
                re.forEach((function(t) {
                    t(e)
                }
                )),
                re = []
            }
        }, ve = function(e) {
            if (e.cancelable) {
                var t = (e.timeStamp > 1e12 ? new Date : performance.now()) - e.timeStamp;
                "pointerdown" == e.type ? function(e, t) {
                    var i = function() {
                        pe(e, t),
                        s()
                    }
                      , r = function() {
                        s()
                    }
                      , s = function() {
                        removeEventListener("pointerup", i, me),
                        removeEventListener("pointercancel", r, me)
                    };
                    addEventListener("pointerup", i, me),
                    addEventListener("pointercancel", r, me)
                }(t, e) : pe(t, e)
            }
        }, ye = function(e) {
            ["mousedown", "keydown", "touchstart", "pointerdown"].forEach((function(t) {
                return e(t, ve, me)
            }
            ))
        }, be = [100, 300], Te = function(e, t) {
            !function(e, t) {
                t = t || {},
                E((function() {
                    var i, r = N(), s = m("FID"), n = function(e) {
                        e.startTime < r.firstHiddenTime && (s.value = e.processingStart - e.startTime,
                        s.entries.push(e),
                        i(!0))
                    }, a = function(e) {
                        e.forEach(n)
                    }, o = f("first-input", a);
                    i = p(e, s, be, t.reportAllChanges),
                    o && (v(y((function() {
                        a(o.takeRecords()),
                        o.disconnect()
                    }
                    ))),
                    d((function() {
                        var r;
                        s = m("FID"),
                        i = p(e, s, be, t.reportAllChanges),
                        re = [],
                        $ = -1,
                        te = null,
                        ye(addEventListener),
                        r = n,
                        re.push(r),
                        ge()
                    }
                    )))
                } come on now
                ))
            }((function(t) {
                var i = function(e) {
                    var t = e.entries[0]
                      , i = {
                        eventTarget: c(t.target),
                        eventType: t.name,
                        eventTime: t.startTime,
                        eventEntry: t,
                        loadState: a(t.startTime)
                    };
                    return Object.assign(e, {
                        attribution: i
                    })
                }(t);
                e(i)
            }
            ), t)
        }
    }
}]);
