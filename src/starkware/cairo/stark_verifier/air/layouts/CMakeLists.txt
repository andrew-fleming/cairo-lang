function(stark_cairo_verifier_layout LAYOUT_NAME)
    python_lib(starkware_cairo_stark_verifier_air_${LAYOUT_NAME}_lib
        PREFIX starkware/cairo/stark_verifier/air/layouts

        FILES
        ${LAYOUT_NAME}/autogenerated.cairo
        ${LAYOUT_NAME}/composition.cairo
        ${LAYOUT_NAME}/global_values.cairo
        ${LAYOUT_NAME}/periodic_columns.cairo
        ${LAYOUT_NAME}/public_verify.cairo
        ${LAYOUT_NAME}/verify.cairo

        LIBS
        starkware_cairo_stark_verifier_core_stark_lib
    )
endfunction()

stark_cairo_verifier_layout(bitwise)
stark_cairo_verifier_layout(dex)
stark_cairo_verifier_layout(perpetual_with_bitwise)
stark_cairo_verifier_layout(recursive)
