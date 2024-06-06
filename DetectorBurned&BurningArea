//VERSION=3
// Detector Burned and current fire area detection

function setup() {
    // Definir la configuración de entrada y salida
    // Entrada: Bandas B02, B03, B04, B08, B11, B12 y dataMask
    // Salida: 4 bandas (R, G, B, Alpha)
    return {
        input: ["B02", "B03", "B04", "B08", "B11", "B12", "dataMask"],
        output: { bands: 4 }
    };
}

function evaluatePixel(samples) {
    // Calcular el Índice de Diferencia Normalizada del Agua (NDWI)
    var NDWI = index(samples.B03, samples.B08); 
    
    // Calcular el Índice de Vegetación de Diferencia Normalizada (NDVI)
    var NDVI = index(samples.B08, samples.B04);
    
    // Calcular un índice personalizado para identificar áreas en llamas
    var INDEX = ((samples.B11 - samples.B12) / (samples.B11 + samples.B12)) + (samples.B08);

    // Condición para identificar tierra (áreas no quemadas)
    // El color gris se calcula como el promedio de las bandas visibles B02, B03 y B04
    if ((INDEX > 0.1) || (samples.B02 > 0.1) || (samples.B11 < 0.1) || (NDVI > 0.3) || (NDWI > 0.1)) {
        var grayValue = 0.25 * (samples.B02 + samples.B03 + samples.B04);
        return [grayValue, grayValue, grayValue, samples.dataMask];
    }
    // Condición para identificar áreas ya quemadas
    // Color amarillo semi-transparente (RGB: [1, 1, 0], Alpha: 0.5)
    else if (INDEX < 0.1 && samples.B12 > 0.2) {
        return [1, 1, 0, 0.5 * samples.dataMask];
    }
    // Condición para identificar incendios activos
    // Color rojo (RGB: [1, 0, 0], Alpha: 1)
    else {
        return [1, 0, 0, samples.dataMask];
    }
}
